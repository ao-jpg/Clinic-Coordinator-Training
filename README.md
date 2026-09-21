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

## Hosting on GitHub Pages

1. Create a repository and push every file in this folder to the root of the repo.
2. In the repo, go to Settings, then Pages.
3. Under Build and deployment, set Source to "Deploy from a branch," pick your branch (usually `main`) and the `/ (root)` folder, and save.
4. The site publishes at `https://<your-username>.github.io/<repo-name>/`.

All links between pages are relative, so the site works as-is once the files sit together in the repo root. The patient-flow video streams from Google Drive, so no large media lives in the repo. No build step, no framework.

## Videos

Videos stream from a shared Google Drive folder, so nothing heavy sits in the repo. Each video is embedded with a Drive preview iframe of the form:

```
https://drive.google.com/file/d/FILE_ID/preview
```

The `FILE_ID` is the long string between `/d/` and `/view` in the file's share link. For any embed to play for outside viewers, the file (or its folder) must be shared as "Anyone with the link, Viewer."

The patient-flow video is already wired into `patient-flow.html`.

### Adding the "how to run the reports" video

`documentation.html` has a styled placeholder for the reports walkthrough. When your video is on Drive, replace the `videoph` block under "Watch: How to run the two reports" with:

```html
<div class="videowrap">
  <div style="position:relative;width:100%;padding-bottom:56.25%;border-radius:10px;overflow:hidden">
    <iframe src="https://drive.google.com/file/d/YOUR_FILE_ID/preview" allow="autoplay" allowfullscreen style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;border-radius:10px"></iframe>
  </div>
</div>
```

Swap `YOUR_FILE_ID` for the reports video's Drive ID and delete the placeholder.

## Editing

Content is plain HTML. Shared look and feel lives in `styles.css`. Each interactive piece (the light-bar demo, the quiz) is a small inline script at the bottom of its own page, so nothing depends on an external library.
