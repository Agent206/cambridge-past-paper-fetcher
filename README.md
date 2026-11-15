# cambridge past paper fetcher

hosted at cppfetcher.netlify.app

A fast, zero-dependency search engine for Cambridge O-Level and A-Level students. Type any past paper, **Examiner Report (`er`)**, **Subject Syllabus (`syllabus`)**, or **upcoming exam component** casually—with typos, student slang, or slash shorthand—and press `Enter` to open the exact official CAIE PDF directly in new tabs.

No more clicking through five nested folders, syllabus directories, or ad walls during exam practice.

---

## What You Can Type

The parser understands natural sentences, exam codes, glued paper/variant tokens (`p2v2`), student slang (`fm`), and heavy typos in under **1ms**:

* **Past Papers (QP & MS):**
  * `a level maths may june 2024 paper 1 variant 2`
  * `fm p2v2 mj 2021`
  * `9709/m/j/24/22` or `4024 s24 12`
* **Examiner Reports (`er` / `examiner report`):**
  * `9702 s23 er`
  * `fm er` *(auto-completes to the latest published Examiner Report)*
  * `chemistry a level 2022 examiner report`
* **Official Subject Syllabus PDFs (`syllabus` / `sy` / Top Toggle):**
  * `a level physics syllabus`
  * `5054 sy`
  * `9709 syllabus 2026`
* **Live Upcoming Exam Schedule (Subject + Paper, No Past Year):**
  * `9702 p12`
  * `math 9709 p32`
  * `further maths p1`
* **Heavy Typos & Swapped Letters:**
  * `maht paper 2 o level my jne 2024 varint 1`

---

## Features

* **Instant QP + MS Dual-Tab Launch:** Toggle **Include MS (`yes` / `no`)** to open both the Question Paper and Mark Scheme simultaneously in separate tabs.
* **Official Syllabus PDF Fetcher:** Flip the top **Past Paper | Syllabus** toggle or type `syllabus` / `sy` in your query to resolve and open the official CAIE syllabus PDF (`{code}_y{range}_sy.pdf`), with 1-click links for every active syllabus year range.
* **Examiner Reports (`ER`) with Cross-Check & Auto-Complete:** Type `er` or `examiner report` directly in Past Paper mode (no extra toggle needed). Cross-checks against HTTP-verified published reports per subject, auto-completes missing session/year to the latest available report, and shows 1-click session chips if a report wasn't published for a specific series.
* **Live Upcoming Exam Schedule & Countdown:** Type a subject and paper number (e.g., `9702 p12`) to automatically view upcoming **Feb/Mar 2027** and **May/June 2027** exam dates, session (`AM` / `PM` / `EV`), component title, duration, and exact **days remaining**—while automatically hiding when you search for a past year's paper.
* **Auto-Detecting Level Slider & Context-Aware `fm` Disambiguation:** Automatically glides between **O-Level** and **A-Level** when it detects a syllabus code (`9709`, `4024`) or single-level subject (`Further Maths`, `Add Maths`), and smartly distinguishes `fm` between **Further Mathematics (9231)** and **Feb/March** based on context.
* **High-Contrast Late-Night Dark Mode:** Switch between the crisp light theme and a high-contrast dark theme via the top-right **Dark / Light** toggle, persisted in `localStorage` with zero flash on load.
* **Interactive `? Help` Cascade Overlay:** Built-in quick-start guide with a GPU-accelerated multi-color diagonal cascade and 1-click testable query chips.
* **Memoized Damerau-Levenshtein + Consonant-Skeleton Parser:** Handles swapped letters (`maht` → `math`, `paepr` → `paper`) and dropped vowels (`my jne` → `May/June`, `vrnt` → `variant`) completely offline.

---

## Tip for Dual Tabs (QP + MS)

Modern browsers block websites from opening two tabs from a single keypress by default.
1. Keep **Include MS** set to `yes` and press `Enter` on your first search.
2. Click the pop-up blocked icon in your browser's address bar and select **"Always allow pop-ups and redirects"** for the site.
3. Every future search will instantly launch both the Question Paper and Mark Scheme side-by-side.

---

## Running Locally & Deploying

The entire application is built inside a single self-contained `index.html` file using Vanilla HTML, CSS, and JavaScript.

### Run Locally
```bash
git clone https://github.com/Agent206/cambridge-past-paper-fetcher.git
cd cambridge-past-paper-fetcher
npx vite
```

