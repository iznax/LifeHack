# LifeHack Journal - Project Overview

## Live Demo
https://iznax.github.io/LifeHack/

## Purpose:
A browser-based journaling and organization app. Users create categories, add text entries, attach images, tag entries with emojis, and export or import their data. All data is stored locally in the browser using localStorage.

## Core Concepts:
- Categories: User-defined groups for organizing entries. Includes a special "Recycle Bin" category.
- Entries: Each entry contains text, timestamp, optional image (base64), and optional emoji tags.
- Tags: Emoji-based labels attached to entries.
- Images: Users can attach images to entries; stored as base64.
- Storage: All data saved in localStorage under the key "lifehackData".

## Main Features:
1. Category Management:
   - Add, rename, delete, reorder categories.
   - Deleting a category moves its entries to Recycle Bin.

2. Entry Management:
   - Add, edit, delete, restore entries.
   - Deleted entries go to Recycle Bin.
   - Permanent deletion only from Recycle Bin.

3. Tags:
   - Emoji picker for selecting tags.
   - Tags can be edited after entry creation.

4. Images:
   - Optional image attachment per entry.
   - Clicking an image opens a modal viewer.

5. Export Options:
   - Per-category: ZIP, text, JSON.
   - Full database: ZIP, JSON, YAML.

6. Import Options:
   - JSON or YAML.
   - Import replaces entire database.

7. UI Structure:
   - Sidebar: categories, add-category input, export/import menu.
   - Main panel: entries for selected category, entry creation area.

## Data Structure:

```json
lifehackData = {
  categories: [...],
  entries: {
    CategoryName: [
      {
        text: "...",
        timestamp: "...",
        image: "...",
        tags: [...],
        edited: true/false,
        originalCategory: "...",
        deletedAt: "..."
      }
    ]
  }
}
```

## AI Guidance Notes:
- Maintain compatibility with the existing localStorage structure.
- Preserve Recycle Bin behavior.
- Keep export/import formats consistent.
- Do not break base64 image handling.
- UI should remain simple and responsive.
