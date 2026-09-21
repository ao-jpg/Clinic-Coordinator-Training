# Alexandria Orthodontics — Clinic Coordinator Training

A multi-page static training site for the Clinic Coordinator role. Two objectives drive it: patient flow (the most important responsibility) and quality control (preparation and documentation).

## Pages

| File | Purpose |
|------|---------|
| `index.html` | Home. The core rule and the two objectives. |
| `patient-flow.html` | Objective 1. Delegation, coverage hierarchy, handoff, light bar, chair rules, radio, staying on time. Embeds the patient-flow video. |
| `preparation.html` | Objective 2, prep side. Pre-arrival setup and quality spot-checks. |
| `documentation.html` | Objective 2, documentation. Five pillars, direction vs shorthand, the coordinator's review role, AI scribes, and the two end-of-day reports. |
| `scenarios.html` | Ten coaching scenarios plus a six-question quiz. |
| `quick-reference.html` | Printable one-page summary. |
| `styles.css` | Shared stylesheet for every page. |
| `patient-flow.mp4` | The delegating-patient-flow video, embedded on the patient-flow page. |

## Hosting on GitHub Pages

1. Create a repository and push every file in this folder to the root of the repo.
2. In the repo, go to Settings, then Pages.
3. Under Build and deployment, set Source to "Deploy from a branch," pick your branch (usually `main`) and the `/ (root)` folder, and save.
4. The site publishes at `https://<your-username>.github.io/<repo-name>/`.

All links between pages are relative, and the video is referenced by filename, so the site works as-is once the files sit together in the repo root. No build step, no framework.

## Adding the "how to run the reports" video

`documentation.html` has a styled placeholder for the reports walkthrough. When your video is ready:

1. Name it `running-reports.mp4` and drop it in this folder.
2. In `documentation.html`, find the `videoph` block under "Watch: How to run the two reports" and replace it with the commented-out `videowrap` markup that sits directly beneath it (the swap-in is already written for you, just uncomment and delete the placeholder).

## A note on video size

`patient-flow.mp4` is about 47 MB. That is under GitHub's 100 MB per-file limit, so it will push and serve fine, but it does make the repo heavier and counts against bandwidth on a busy site. Two lighter options if you want them:

- Host the video on an unlisted YouTube or Vimeo link and swap the `<video>` tag for an `<iframe>` embed.
- Keep large media out of Git history with Git LFS.

Either is optional. As delivered, the file plays directly from the repo.

## Editing

Content is plain HTML. Shared look and feel lives in `styles.css`. Each interactive piece (the light-bar demo, the quiz) is a small inline script at the bottom of its own page, so nothing depends on an external library.
