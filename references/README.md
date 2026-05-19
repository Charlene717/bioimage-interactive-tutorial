# Bioimage Analysis · References

This subfolder hosts a single `index.html` that lists the academic papers, official docs, benchmarks, and database / model references behind every topic in `../`.

## Structure

The page is organised by tutorial step (Step 1 through Step 9 + 4 advanced modules + seminal reviews / textbooks). Each entry includes a `.ref-tag` indicating type:

| Tag | Meaning |
|---|---|
| **paper** | Primary peer-reviewed publication |
| **doc** | Official documentation / source repository |
| **bestp** | Best-practice review or community guideline |
| **bench** | Independent benchmark / method comparison |
| **db** | Image / model / annotation database |
| **book** | Textbook or reference book |

DOIs are linked through doi.org and were verified in May 2026. ArXiv links are provided where appropriate (foundation models, preprints).

## Adding a new reference

1. Locate the appropriate section anchor (`#s1` through `#s13` or `#sreviews`)
2. Add a `<li>` with the right `.ref-tag`, author, italic title, journal info, and DOI link
3. Follow the existing pattern for spacing and punctuation
