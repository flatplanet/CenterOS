# {{WIKI_NAME}} Wiki

A personal knowledge base maintained by [AI_NAME].
Based on Andrej Karpathy's LLM Wiki pattern.

## Purpose

This wiki is a structured, interlinked knowledge base for {{WIKI_TOPIC}}.
[AI_NAME] maintains the wiki. [PRINCIPAL] curates sources, asks questions, and guides the analysis.

## Folder Structure

```
raw/           -- source documents, immutable
wiki/          -- markdown pages maintained by [AI_NAME]
wiki/index.md  -- table of contents for the entire wiki
LOG.md         -- append-only record of all operations at the wiki root
```

## Ingest Workflow

When the user adds a new source to `raw/` and asks you to ingest it:

1. Read the full source document.
2. Discuss key takeaways with the user before writing anything.
3. Create a summary page in `wiki/` named after the source.
4. Create or update concept pages for each major idea or entity.
5. Add wiki-links like `[[page-name]]` to connect related pages.
6. Update `wiki/index.md` with new pages and one-line descriptions.
7. Append an entry to `LOG.md` with the date, source name, and what changed.

A single source may touch 10 to 15 wiki pages. That is normal.

## Page Format

Every wiki page should follow this structure:

```markdown
# Page Title

**Summary**: One to two sentences describing this page.

**Sources**: List of raw source files this page draws from.

**Last updated**: Date of most recent update.

---

Main content goes here. Use clear headings and short paragraphs.

Link to related concepts using [[wiki-links]] throughout the text.

## Related pages

- [[related-concept-1]]
- [[related-concept-2]]
```

## Citation Rules

- Every factual claim should reference its source file.
- Use the format `(source: filename.pdf)` after the claim.
- If two sources disagree, note the contradiction explicitly.
- If a claim has no source, mark it as needing verification.

## Question Answering

When the user asks a question:

1. Read `wiki/index.md` first to find relevant pages.
2. Read those pages and synthesize an answer.
3. Cite specific wiki pages in your response.
4. If the answer is not in the wiki, say so clearly.
5. If the answer is valuable, offer to save it as a new wiki page.

Good answers should be filed back into the wiki so they compound over time.

## Lint

When the user asks you to lint or audit the wiki:

- Check for contradictions between pages.
- Find orphan pages with no inbound links from other pages.
- Identify concepts mentioned in pages that lack their own page.
- Flag claims that may be outdated based on newer sources.
- Check that all pages follow the page format above.
- Report findings as a numbered list with suggested fixes.

## Rules

- Never modify anything in the `raw/` folder.
- Always update `wiki/index.md` and `LOG.md` after changes.
- Keep page names lowercase with hyphens, such as `machine-learning.md`.
- Write in clear, plain language.
- When uncertain about how to categorize something, ask the user.
