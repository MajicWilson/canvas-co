---
name: customer-favorites
description: Find Canvas & Co's top 4 products by order count and the testimonials that mention them, using the latest sales and testimonials data from Google Drive, and save the result to customer-favorites.md. Use when the user asks to update, regenerate, or refresh customer favorites, top products, or bestsellers.
---

# Customer favorites

Regenerate `customer-favorites.md` at the repo root from the latest sales and
testimonials data in the "Canvas & Co Sales" Google Drive folder.

## Steps

1. **Find the source files in Drive.** Search Drive (`search_files`) for files
   titled `sales` and `testimonials`. There may be more than one sales-shaped
   file (e.g. an older or differently-formatted export) — prefer the file
   whose schema matches the columns below and whose `modifiedTime` is most
   recent. Don't average or merge multiple sales files together.
   - `sales`: `order_id,date,customer_name,email,category,product,quantity,unit_price,line_total`
   - `testimonials`: `date,customer_name,location,product,rating,quote`
2. **Read both files in full** with `read_file_content` (not just the search
   snippet, which can be truncated).
3. **Count orders per product.** Count the number of order rows per product
   (one order = one row), not units sold and not revenue. Rank products by
   that count, highest first.
4. **Take the top 4 products.** If there's a tie at the 4th-place cutoff,
   include all tied products (so the list may have more than 4 entries) and
   say in the output that they're tied.
5. **Collect testimonials for those products.** Pull every testimonial row
   whose `product` matches one of the top products, and quote it verbatim
   with the customer's name and location as given in the testimonials sheet.
6. **Write `customer-favorites.md`** at the repo root (overwrite if it
   exists) with:
   - A short header noting this is order-count ranking (not revenue/units)
     and which source files/dates it came from.
   - One section per top product, `## <rank>. <Product> — <N> orders`,
     followed by its testimonial quotes as blockquotes
     (`> "<quote>" — <name>, <location>`).
   - If a product has no matching testimonials, say so under its heading
     rather than omitting the section.

## Privacy

`sales.csv`/the sales sheet contains customer names and emails tied to
individual orders — see `CLAUDE.md`. Only use it to compute counts. Never
copy customer names or emails from the *sales* data into
`customer-favorites.md`; names/locations in the output should only come from
the testimonials sheet, where the customer already agreed to be quoted
publicly.
