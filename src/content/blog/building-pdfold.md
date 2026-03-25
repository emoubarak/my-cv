---
title: "Building PDFold — A Multi-Pass AI Pipeline for Document Understanding"
description: "How I designed and shipped an AI-powered SaaS that converts scanned documents into structured Markdown using OCR, layout analysis, and the Gemini API."
pubDate: 2026-03-15
tags: ["AI", "SaaS", "Next.js", "TypeScript"]
---

# Building PDFold — A Multi-Pass AI Pipeline

Building a document understanding pipeline is deceptively complex. Here's how I approached it.

## The Problem

Most OCR tools give you raw text. They don't understand layout, hierarchy, or semantic meaning. PDFold was born from the frustration of dealing with poorly-converted PDFs.

## The Architecture

The pipeline works in three distinct passes:

1. **OCR Pass** — Extract raw text and bounding boxes from scanned images
2. **Layout Understanding** — Use vision models to identify headers, tables, lists, and content blocks
3. **Structured Generation** — Convert the understood layout into clean, semantic Markdown

```typescript
async function processPDF(file: Buffer): Promise<string> {
  const pages = await extractPages(file);
  const ocrResults = await Promise.all(pages.map(ocrPass));
  const layouts = await Promise.all(ocrResults.map(layoutPass));
  return layouts.map(generateMarkdown).join('\n\n---\n\n');
}
```

## Lessons Learned

- **Multi-modal is the future**: Combining vision and language models produces drastically better results than either alone.
- **Freemium works**: Offering 5 free conversions per month drives organic growth.
- **Ship fast, iterate**: The first version was rough, but real user feedback is worth more than any amount of internal testing.

> "We don't see the world as it is, but as we are." — This applies to product development too.
