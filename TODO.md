# Website Update Plan — Winter 2026/27

Original status survey from July 2026; reference checks updated on November 2, 2026. Work through section by section alongside the semester.

## 1. Repo cleaning (do once, before the semester)

- [ ] `basics/index.qmd` is an **empty 0-byte file**, orphaned (not in sidebar, not linked anywhere). Delete it or write a real "Basics" landing page.
- [ ] Remove committed render artifacts: `notebooks/*.ipynb.html` (7 files) and `.DS_Store`; add `*.ipynb.html` and `.DS_Store` to `.gitignore`.
- [ ] `processing/bert_classification.ipynb` is **6.5 MB** (saved outputs). Strip heavy outputs and consider moving it to `notebooks/` for consistency (sidebar + embeds would need updating).
- [ ] Duplicate notebooks: `literature-review.ipynb` vs `literature-review-v2.ipynb` (only v2 is used); `2023_12_11_GPT_Text_Classification.ipynb` + `2`, `3`, `4`. Archive/delete the superseded ones.
- [ ] Decide fate of the disabled blog scaffold (`blog.qmd`, `posts/` with only `_metadata.yml`): remove, or launch it as a changelog for the weekly updates.
- [ ] Decide promote-vs-retire for pages linked in content but missing from the sidebar:
  - `evaluation/label-studio-images.qmd` (linked from 3 pages) — probably promote to sidebar under Evaluation.
  - `image-analysis/ensemble.qmd` and `image-analysis/gephi.qmd` (soft-orphans, linked from exploration/classification).
  - `processing/archive/saving.qmd` (linked from classification.qmd).

## 2. Site-wide fixes

- [ ] Home page (`index.qmd`): says "third iteration (Winter 2025/26)" and "Updates 2025/26" — bump to Winter 2026/27; reset the ✨/🚀/🔧 markers for the new round.
- [ ] Home page blurb for Instagram Posts still says "using instaloader, CrowdTangle, or Zeeschuimer" — CrowdTangle shut down in 2024, instaloader is not recommended; reword.
- [ ] Enable sidebar search in `_quarto.yml` (`search: false` → `true`) — cheap win for students.
- [ ] Navbar: Twitter icon/handle → X, or replace with Bluesky/Mastodon/LinkedIn; verify Threads link still correct.
- [ ] Sweep stale time-bound prose: "As of November 2024…", "preferred approach for the 2024/25 winter semester", "During Winter 2025/26 semester…" (basics/openai.qmd, evaluation/index.qmd, others).
- [ ] Frontmatter `date:` fields stuck at 2023/2024 on many pages — either update per rewrite or add `date-modified` so pages show freshness automatically.
- [ ] After the semester update: mint a new Zenodo version and check the GPLv3 link (points at supplement repo tag `v0.0.1`).

## 3. Notebook/embed drift (breaks trust in the material)

Verification (November 2, 2026): after the full build and targeted resource
renders, all 28 rendered content pages pass local file and anchor checks.
Reporting images and evaluation notebook links were inspected in the browser;
interactive evaluation examples were revised and checked separately below.
Notebooks were not executed.

- [x] `evaluation/agreement.qmd`: prominently link V3 in Colab and on GitHub instead of embedding the notebook. Remove the local copy added solely for embedding. Historical versions remain linked.
- [x] `reporting/index.qmd`: add the missing `.png` image suffix. Verified that the local Statistical Analysis copy intentionally links to the existing `2024_02_05_Reporting.ipynb` in the supplement; no URL change needed.
- [x] `processing/preprocessing.qmd`: correct the Preprocessing notebook URL in `notebook-view` metadata.
- [x] `processing/classification.qmd`: distinguish the four snippet titles by purpose. They link to the same full source notebook in the supplement; numbered local snippets are not separate upstream notebooks.
- [ ] `basics/openai.qmd`: mixed image paths (`/images/...` vs `../images/...`); unfinished "Future Work" checklist (Track Spending, Response Formats, Batch Processing) — finish or remove.
- [x] Verified Visual BERTopic references in `image-analysis/exploration.qmd`: local embeds exist; the differently named upstream notebook URL also exists. No path change needed.
- [ ] Investigate full-render resource copying with Quarto 1.9.38: the full build succeeds but omits OJS and blog-listing libraries; targeted renders of `evaluation/agreement.qmd` and `blog.qmd` restore them. Resolve the empty blog-listing warning with the blog scaffold decision in §1. Notebook execution and exhaustive external-link checks are not part of this verification.
- [x] `data-collection/ig-posts.qmd`: correct the reversed Digital Methods Initiative link and restore stable anchors for Zeeschuimer, Instaloader, and CrowdTangle.
- [x] Repair stale section links in evaluation, visual analysis, related work, and theory. Escape an Instagram handle in a saved Markdown output so Quarto does not treat it as a citation; displayed text is unchanged. Fix the embedded archive example image to use a site-root path.
- [ ] `data-collection/index.qmd` (~line 48): duplicated sentence — "These can lower technical complexity.These lower technical overhead but…" — keep one.
- [ ] `data-collection/ig-stories.qmd`: "brow~er" typo in image alt text (line 25); step list jumps 1 → 4 → 5 (lines 37–39); "normal user und archive" German/English mix (line 60).

## 4. Content updates, week by week (suggested order = course order)

### Getting Started
- [ ] `getting-started/index.qmd`: new 2026/27 schedule, dates, deliverables.
- [ ] `related-work.qmd`: add 2024–2026 literature (post-API data access, LLM annotation/classification studies, multimodal election research).
- [ ] `literature-review-v2.ipynb` (marked 📦 archived): either retire visibly or refresh with current API + structured outputs.

### Basics
- [ ] `tools.qmd`: frontmatter date 2023-10-30, references "tools session (October 30th)" WiSe 2023/24 — full refresh. Reconsider tool list (Colab still primary? Obsidian still recommended?).
- [ ] `openai.qmd`: no model is named, playground screenshots are old; update for the current OpenAI platform (projects, current model lineup, structured outputs, Batch API for cheap classification). **Consider broadening beyond OpenAI** — the whole site is OpenAI-only; at minimum mention alternatives (Anthropic, Gemini, open-weight models via Ollama/HF) and academic/data-protection considerations.

### Data Collection
- [ ] `index.qmd` (Post-API World, updated Nov 2025): verify DSA Art. 40 status for 2026 — researcher data access is now operational; add pointers to the application process (Meta Content Library, TikTok Research API/VCE, YouTube Researcher Program).
- [ ] `ig-posts.qmd`: CrowdTangle section → archive callout only; verify Zeeschuimer + 4CAT instructions/screenshots against current versions; check instaloader status (archived).
- [ ] `ig-stories.qmd`: verify Tidal Tales still works against current Instagram; update screenshots.
- [ ] TikTok is only an external Google-Docs link (check it's still alive) — consider an own TikTok chapter (see §5).

### Text Analysis
- [ ] `preprocessing.qmd`: Whisper notebook — consider faster-whisper or the API-based route; verify OCR approach (or replace OCR+Whisper with a single multimodal-LLM pass).
- [ ] `exploration.qmd`: BERTopic still fine; GPT-exploration notebook uses 2023-era models (`gpt-3.5-turbo`, `gpt-4`) — re-run with current models.
- [ ] `classification.qmd`: core chapter, references `gpt-3.5`/`gpt-4`/`gpt-4-turbo` — update to current models, add structured outputs (JSON schema) instead of prompt-parsing, add Batch API for cost, mention open-weight LLM classification as a reproducible alternative.
- [ ] `bert_classification.ipynb`: consider ModernBERT (or a current German-capable encoder) instead of classic BERT; mention SetFit for few-shot.

### Image Analysis (marked 🔧 site-wide — biggest refresh)
- [ ] `exploration.qmd`: commercial Vision APIs (Google Vision labeling) are largely superseded by multimodal LLMs — restructure; k-means/CLIP-embedding clustering still good.
- [ ] `classification.qmd`: "multimodal GPT-4" / GPT-4V is deprecated — rewrite on current multimodal models; CLIP notebook still fine, mention SigLIP as modern alternative.
- [ ] `ensemble.qmd`: the ensemble (OCR + object detection + captioning → GPT) is mostly obsoleted by native multimodal models — reframe as historical/archived or as a cost-optimization pattern.
- [ ] `gephi.qmd`: verify Gephi version + Image Preview plugin still exist; decide sidebar promotion or archive.

### Evaluation / Reporting
- [x] Quality-check `evaluation/agreement.qmd`: deterministic Kappa example, nominal alpha and missing-data examples, consistent confusion-matrix axes, recall and distinct binary/macro F1, explicit undefined values, calculated reporting table, and development/test separation. Checked 2,626 Kappa settings plus boundary cases; 256 metric combinations against scikit-learn; Python examples against scikit-learn and `krippendorff`. Temporary checks added no repository dependencies.
- [x] Replace the stale evaluation embed with prominent V3 links (see §3). Review evaluation concepts and examples for accuracy; do not assume existing explanations are correct merely because the metrics are established.
- [ ] Consider adding: validating LLM annotations specifically (LLM-as-annotator literature 2024–2026, stability across model versions/temperature, reporting model+version+prompt in papers).
- [ ] `reporting/index.qmd` (Feb 2024): fix broken image, refresh statistical-analysis notebook.
- [ ] `projects/index.qmd` (Jan 2024): add student projects/publications from the 2024/25 and 2025/26 iterations.

## 5. Missing chapters / new content candidates

- [ ] **DSA Art. 40 hands-on chapter** — the biggest post-2025 shift: how researchers actually apply for and use Meta Content Library, TikTok Research API/VCE. Natural companion to the Post-API World page.
- [ ] **Bluesky chapter** — open API, no auth hurdles, ideal for teaching data collection; fills the gap left by X/Twitter.
- [ ] **Video analysis chapter** — visual social media is video-first (Reels/TikTok/Shorts); currently only Whisper covers audio. Frame sampling + multimodal LLM classification would modernize the "visual" core of the seminar.
- [ ] **Local/open-weight LLMs chapter** — classification with Ollama/HF models: reproducibility, GDPR, cost; increasingly expected in methods sections.
- [ ] **AI-generated content / synthetic media** — detection and prevalence in political communication; highly relevant for a political-communication seminar in 2026.
- [ ] **Agentic/automated pipelines** (optional): orchestrating collection→classification→validation with current tooling.
- [ ] TikTok data collection as a first-class page instead of the external Google-Docs link.
