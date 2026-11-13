# cambridge past paper fetcher

A fast, zero-dependency search engine for Cambridge O-Level and A-Level students. Type any paper casually—with typos, student slang, or slash shorthand—and press `Enter` to open the exact **Question Paper (QP)** and **Mark Scheme (MS)** PDFs directly in new tabs.

No more clicking through five nested folders, syllabus directories, or ad walls during exam practice.

---

## What You Can Type

The parser understands natural sentences, exam codes, student slang, and heavy typos in under **1ms**:

* **Casual Natural Search:**
  * `a level maths may june 2024 paper 1 variant 2`
  * `o level physics oct nov 2023 p2 v1`
* **Slash & Code Shorthand (Any Order):**
  * `9709/m/j/24/22`
  * `9702/22/26/m/j`
  * `4024 s24 12`
* **Student Slang & Nicknames:**
  * `further maths m/j 24 p1 v2`
  * `add maths oct nov 23 p2 v2`
  * `pak studies may june 24 p1 v1`
  * `comp sci 2024 may june p1 v2`
* **Heavy Typos & Swapped Letters:**
  * `maht paper 2 o level my jne 2024 varint 1`

---

## Features

* **Instant QP + MS Dual-Tab Launch:** Toggle **Include MS (`yes` / `no`)** to open both the Question Paper and Mark Scheme simultaneously in separate tabs.
* **Auto-Detecting Level Slider:** Automatically glides between **O-Level** and **A-Level** when it detects a syllabus code (`9709`, `4024`) or single-level subject (`Further Maths`, `Add Maths`), or lets you lock your level so you never have to type it.
* **Damerau-Levenshtein + Consonant-Skeleton Parser:** Handles swapped letters (`maht` → `math`, `paepr` → `paper`) and dropped vowels (`my jne` → `May/June`, `vrnt` → `variant`) completely offline without heavy AI downloads.
* **Pre-Redirect CAIE Syllabus Validator:** Verifies that the paper number, variant (`1–3`, or `1–5` for A-Level Science practicals), session (`Feb/March` rules), and syllabus year range (`2002–2026`) actually exist before opening a tab.
* **Live Checkmark Pills & Code Preview:** Ticks off `Level`, `Subject`, `Session`, `Year`, `Paper`, and `Variant` in real time as you type and previews the exact target filename (`9709_s24_qp+ms_22`) inside the search bar.
* **On-Demand Extended Catalog:** Preloads core O/A Level subjects in memory and dynamically caches extended or custom 4-digit syllabus codes to `localStorage`.

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
git clone [https://github.com/Agent206/cambridge-past-paper-fetcher.git](https://github.com/Agent206/cambridge-past-paper-fetcher.git)
cd cambridge-past-paper-fetcher
