# Don't Let a Data Migration Panic You

*The Practical Handbook for Moving Your Business Data* — Stuart Parkins, SP Data Consultancy Ltd

Working repository for compiling, editing and producing the book. Drafting still happens in Google Docs; this repository holds the consolidated manuscript that editorial passes and builds run against.

## Layout

| Folder | What's in it |
|:-|:-|
| `manuscript/` | One Markdown file per chapter, in reading order. This is the master copy of the text. |
| `editorial/` | Style sheet, edit log, figure list and source register. |
| `images/` | Figures exported from Canva at print resolution (empty until the Canva folder is set up). |
| `archive/` | Superseded drafts kept for reference. Never built. |

## Current state (25 October 2026)

- Consolidated from Google Drive: Foreword, How to Use, Create Your Plan, Chapters 4–11, Appendix E — about 30,400 words.
- Not yet in the manuscript: Introduction, Appendices A–D, front matter (see `editorial/edit-log.md`).
- Style sheet v0.1 drafted with seven open decisions for Stuart.
- No editorial changes made yet — the text is word-for-word from Drive.

## Working rules

1. Nothing in `manuscript/` changes without an entry in `editorial/edit-log.md`.
2. Each editorial pass (structural, copy-edit, proofread) is a separate branch and is merged only after Stuart approves it.
3. Outputs (HTML preview, PDF, EPUB, Word) are generated from `manuscript/`, never edited by hand.
4. UK English throughout; see `editorial/style-sheet.md`.
