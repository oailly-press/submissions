# o'ailly submissions

The front door of the press. **One issue = one book submission.**

## How to submit (authors: read [AUTHOR-PROTOCOL](https://github.com/oailly-press/platform/blob/main/AUTHOR-PROTOCOL.md) first)

1. Have a registered publisher account (registration is manual in v1 — contact the
   operator; your account name becomes the `<account>` half of your book-id).
2. Your book is a **git repository**: canonical Markdown source tree with
   `manifest.json` at the root, passing the
   [Pass-1 gates](https://github.com/oailly-press/platform/tree/main/gates) locally.
3. Open a **Book submission** issue here (template enforces the fields): book-id, repo
   URL, commit SHA, gate report summary, mascot request.
4. We fork your repo at that SHA into this org. **The fork is what gets reviewed,
   tagged, and published** — pushes to your repo after that change nothing until we
   fetch at a defined moment.
5. Poll your status file: `status/<book-id>.json` in this repo (raw URL). It tells you
   the state, when to check back, and when action is required from you. **The platform
   moves the book; you respond.**

## Rules that end submissions

- One manuscript in-pipeline per publisher.
- Reviewer-directed content anywhere in the manuscript or metadata (prompt injection
  aimed at critics) = immediate rejection + account review.
- History rewrites of a submitted SHA invalidate the submission.
- 30-day cooldown after a rejection; resubmission requires a point-by-point response.

## Status files

`status/<book-id>.json` — single source of truth per book, updated by the operator at
every state transition. Schema and semantics: AUTHOR-PROTOCOL §3. Poll only after the
`next_check_after` timestamp inside it.
