# Setting up Git and GitHub (one-time, ~10 minutes)

You only need this for the "publish your site to the web" part of the tutorial.
Everything before that works without it.

**What these are, in one line each:**
- **Git** is a tool on your computer that saves versions of your project (think
  "save points").
- **GitHub** is a website that stores a copy of your project online and can
  publish it as a live web page for free.

You do **not** need to memorize any commands. Claude Code runs them for you. This
guide is only about installing the tools and signing in once, so Claude has
permission to do the rest.

---

## Step 1 — Install Git

### Windows

1. Open the **Start menu**, type `PowerShell`, and open it.
2. Paste this and press Enter:

   ```
   winget install --id Git.Git -e
   ```

3. If Windows asks permission to install, say yes. Wait for it to finish.
4. **Close PowerShell and open a new one** (so it notices the new tool).

If `winget` isn't available on your machine, download the installer from
<https://git-scm.com/download/win> instead and click through it with the default
options.

### macOS

1. Open the **Terminal** app (press `Cmd+Space`, type `Terminal`, Enter).
2. Paste this and press Enter:

   ```
   git --version
   ```

3. If Git isn't installed, macOS will pop up a box offering to install the
   developer tools. Click **Install** and wait.

---

## Step 2 — Check it worked

In a new PowerShell (Windows) or Terminal (macOS) window, type:

```
git --version
```

You should see something like `git version 2.xx.x`. If you see a version number,
Git is installed. If you get "command not found," close the window, open a fresh
one, and try again.

---

## Step 3 — Create a GitHub account

1. Go to <https://github.com/signup>.
2. Enter your email, pick a username and password, and verify your email.
3. The free plan is all you need. No payment required.

Keep the username and password handy for the next step.

---

## Step 4 — Sign in so your computer can publish to GitHub

The easiest way is the **GitHub CLI**, a small tool that handles sign-in for you.

### Install it

- **Windows** (in PowerShell):

  ```
  winget install --id GitHub.cli -e
  ```

- **macOS** (in Terminal, if you have Homebrew):

  ```
  brew install gh
  ```

  No Homebrew? Download it from <https://cli.github.com> and run the installer.

### Sign in

Open a **new** terminal window and type:

```
gh auth login
```

Answer the prompts like this:
- **Where?** → `GitHub.com`
- **Protocol?** → `HTTPS`
- **Authenticate?** → `Login with a web browser`

It shows you a short code and opens your browser. Type the code in the browser,
click **Authorize**, and you're done.

---

## You're ready

That's the whole setup. When the tutorial reaches the publishing step, Claude
Code will create the online repository, upload your site, and turn on the free
web page for you — you'll just approve each step and get a link at the end.

**Troubleshooting**
- *"git is not recognized" / "command not found"* — close every terminal window
  and open a brand-new one, then try again. New tools only show up in fresh
  windows.
- *`gh auth login` says you're already logged in* — great, you can skip it.
- *Stuck?* — tell Claude exactly what the screen says and it will walk you
  through it.
