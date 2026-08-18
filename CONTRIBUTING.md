# Contributing: editing card text

This guide is for anyone who wants to edit the text on the survey result cards (headlines, labels, stats, or the flip-side explanation text) but doesn't write code. No local setup is needed — everything below can be done in the GitHub website.

## 1. Get set up (one-time)

- **GitHub account**: sign up free at [github.com](https://github.com) if you don't have one.
- **Fork the repo**: go to [github.com/schoolofcities/mobilizing-justice](https://github.com/schoolofcities/mobilizing-justice) and click "Fork" (top right) — this makes your own copy you can edit.
- **Keep your fork up to date**: if you already forked the repo previously, sync it before starting a new edit — on your fork's GitHub page, click "Sync fork" (or "Fetch upstream") to pull in the latest changes before you start.
- **Pull request basics**: if you haven't opened a PR before, GitHub's guide is a good primer: [Creating a pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request). In short: edit a file in your fork → GitHub offers to "Propose changes" → open a PR back to this repo → it gets reviewed and merged.

## 2. Where the pages live

Each of the 8 survey topics are contained in their own file:

```
src/routes/national-survey/<topic-name>/+page.svelte
```

Topics: `age`, `disabilities`, `ethnicity`, `gender`, `immigration`, `income`, `transit-proximity`.

For example, to edit the Disabilities page, open:
`src/routes/national-survey/disabilities/+page.svelte`

## 3. What's safe to edit in each file

The editable text lives in a few specific spots. (Try to leave everything else alone, as it might break formatting/layout)

- **Page intro text** — inside `<div class="text"> <p> ... </p> </div>` near the top (and sometimes a footnote `<p class="data-note">` near the bottom).
- **Each card** is a block like `<StatCardBars ...> ... </StatCardBars>` (or `StatCardStack`, `StatCardTwoSquares`, `StatCardGrid`). Within each card block, only edit the text **inside quotation marks** for these properties:
  - `context="..."` — the headline/summary shown on the card
  - `label: "..."` — the labels for each stat/bar being compared
  - `stat: "..."` — the number itself (e.g. `"42%"`)
  - `sharedLabel="..."` or the `label:` inside `groups` — the axis/legend caption
  - `backText="..."` — the longer explanation shown on the flip side of the card (this contains a `<p>...</p>` — only edit the sentence inside the `<p>` tags, not the tags themselves)

**Rule of thumb:** only change text that sits between quote marks (`"..."`) or between `<p>` and `</p>`. Never touch anything outside quotes — brackets `{ }`, commas, `color:`, component names, `<StatCardBars>`, `icon={...}`, etc. all need to stay exactly as they are, or the page will break.

## 4. Example of a safe edit

```svelte
<StatCardBars
    icon={iconCar}
    context="Road safety concerns affect individuals with disabilities more"   <!-- editable -->
    groups={[
        {
            label: "Agreed or strongly agreed that they feel safe...(%)",     <!-- editable -->
            bars: [
                { label: "Individuals with disabilities*", value: 38 },       <!-- label editable, value editable -->
                { label: "Individuals without disabilities", value: 51 }      <!-- label editable, value editable -->
            ]
        }
    ]}
    colors={['var(--mjYellow)', 'var(--mjGreen)']}   <!-- do not touch -->
    backText="
        <p>
            The share of individuals with disabilities...   <!-- editable -->
        </p>
    "
/>
```

## 5. Submitting the change

1. On GitHub, navigate to the file, click the pencil (✏️) icon to edit directly in the browser.
2. Make your text changes.
3. Scroll down, add a short commit message (e.g. "Update disabilities card text"), choose "Create a new branch and start a pull request."
4. Click "Propose changes" → "Create pull request."
5. A maintainer will review and merge it.

## A few extra notes

- **Quotes inside your text**: if your edited text needs a `"` inside it, avoid it or use a `'` instead — a stray `"` will break the code.
- **Don't touch numbers unless updating data**: `value:` and `stat:` fields drive the chart itself — text-only edits shouldn't change these unless the underlying stat actually changed.
- **No live preview**: GitHub's web editor doesn't render the actual page, so a maintainer should review the rendered page before merging. If you are interested in having a live preview, read below.

## Local development (optional)

If you'd like to see your changes rendered on the actual page before opening a PR, you can run the site locally. This requires some knowledge of working in terminal/command line on your computer.

1. **Install Node.js**: download and install the current LTS version from [nodejs.org](https://nodejs.org) (this includes `npm`). Node 20 or later is recommended.
2. **Clone the repo**: instead of editing in the browser, clone your fork to your computer:
   ```
   git clone https://github.com/<your-username>/mobilizing-justice.git
   cd mobilizing-justice
   ```
3. **Install dependencies**:
   ```
   npm install
   ```
4. **Create a branch** for your edit, rather than working directly on `main`:
   ```
   git checkout -b update-disabilities-text
   ```
   (Use a short descriptive name for the branch — this keeps your change isolated and makes future edits easier to manage.)
5. **Run the dev server**:
   ```
   npm run dev
   ```
   This prints a local URL (usually `http://localhost:5173`) — open it in your browser to see the site. It will automatically reload as you edit and save files, so you can check your card text changes as you make them.
6. **Edit the file** (e.g. in VS Code, or any text editor) and save it.
7. **Commit and push your changes** from the terminal, inside the `mobilizing-justice` folder:
   ```
   git add src/routes/national-survey/disabilities/+page.svelte
   git commit -m "Update disabilities card text"
   git push -u origin update-disabilities-text
   ```
   (Replace the file path with whichever file you edited, and use the same branch name you created in step 4.)
8. **Open a pull request**: go to your fork on GitHub — it will usually show a banner offering to "Compare & pull request" for the branch you just pushed. Click it, review the changes, and submit the PR.


