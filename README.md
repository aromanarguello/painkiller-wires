# Painkiller Wireframes

Live interactive prototype for the Painkiller product design.

**Live site:** https://painkiller-wires.vercel.app
Every time you push changes, the live site updates automatically (takes about 10 seconds).

---

## First-Time Setup (do this once)

### 1. Install the tools you need

You need two things installed: **Git** (to sync your changes) and **Claude Code** (to help you edit).

**Check if Git is installed** — open Terminal and type:
```
git --version
```
If you see a version number, you're good. If not, macOS will prompt you to install it — follow the prompts.

**Install Claude Code** — if you don't have it yet:
```
npm install -g @anthropic-ai/claude-code
```
(If `npm` isn't installed, install Node.js first from https://nodejs.org — download the LTS version and run the installer.)

### 2. Clone the project to your computer

This downloads the project files to your machine. Open Terminal and run:

```
cd ~/Desktop
git clone https://github.com/aromanarguello/painkiller-wires.git
```

This creates a folder called `painkiller-wires` on your Desktop. You only do this once.

### 3. Verify it works

Open the folder and double-click `index.html` — it should open in your browser and show the wireframes with a dark toolbar at the top for switching between screens.

---

## Daily Workflow

Every time you want to make changes, this is the process:

### Step 1: Open the project in Claude Code

Open Terminal and run:
```
cd ~/Desktop/painkiller-wires
claude
```

This opens Claude Code inside the project. It automatically reads the instructions file (`CLAUDE.md`) so it understands the wireframe structure.

### Step 2: Tell Claude Code what you want to change

Just describe what you want in plain language. Examples:

- "Change the hero text on the landing page to say 'Your home, simplified'"
- "Add a new card to the dashboard for upcoming maintenance"
- "Make the pricing section show three tiers instead of two"
- "Add a new screen for account settings"
- "Change the green color to a brighter green"

Claude Code will edit `index.html` for you.

### Step 3: Preview your changes

Open (or refresh) `index.html` in your browser to see how the changes look. Use the dark toolbar at the top to switch between screens.

If something doesn't look right, tell Claude Code what to fix — keep going until you're happy.

### Step 4: Push to deploy

When you're happy with the changes, tell Claude Code:

> "Commit and push these changes"

Or describe what you did:

> "Push this — I updated the dashboard layout"

Claude Code will save your changes and push them to GitHub. The live site updates automatically within about 10 seconds.

### Step 5: Check the live site

Go to https://painkiller-wires.vercel.app and refresh. You should see your changes live.

---

## If Something Goes Wrong

**"I messed something up and want to undo"**
Tell Claude Code: "Undo my last change" or "Revert the last commit"

**"The site isn't updating after I push"**
Wait 30 seconds and refresh. If still not updated, tell Claude Code: "Check if the last push went through"

**"I can't push — it says something about conflicts"**
Tell Claude Code: "I'm getting a conflict when I try to push, help me fix it"

**"I accidentally closed Terminal"**
Just open Terminal again and run:
```
cd ~/Desktop/painkiller-wires
claude
```

---

## Quick Reference

| What you want to do | What to tell Claude Code |
|---|---|
| Edit text or layout | "Change [thing] to [new thing]" |
| Add something new | "Add a [component] to the [screen] screen" |
| Change colors/fonts | "Change the [color/font] to [new value]" |
| Add a new screen | "Add a new screen called [name] with [description]" |
| Preview changes | Open `index.html` in your browser |
| Deploy | "Commit and push these changes" |
| Undo | "Undo my last change" |
