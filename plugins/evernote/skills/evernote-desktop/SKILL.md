---
name: evernote
description: Use Evernote desktop or Evernote Web to search, read, summarize, organize, and draft changes to notes. Use when the user asks to work with Evernote or an Evernote note.
---

# Evernote desktop and Web workflows

Use this skill when the user asks to find, read, summarize, organize, create, or edit content in Evernote.

## Choose a mode

- If the user says “desktop app,” “desktop,” or “native app,” use the installed Evernote desktop app only.
- If the user says “Web,” “browser,” or “website,” use Evernote Web only at `https://www.evernote.com/client/web`.
- If the user does not specify a mode, prefer the desktop app when it is installed and accessible. Use Evernote Web only as a fallback when the desktop app is unavailable or the user agrees.
- Never silently perform a write in both modes. If the user asks to compare or synchronize desktop and Web, read both first, explain any differences, and confirm the exact target and change before writing.

## Access

- Use native desktop app control and accessibility/UI inspection for the installed app named `Evernote`.
- If desktop mode is selected and Evernote is not open, launch the desktop app. Never ask the user to share credentials, session cookies, or one-time codes.
- If Web mode is selected, open the Evernote Web URL in a browser and let the user sign in if needed. Never ask for credentials, session cookies, or one-time codes.
- Confirm that the visible account, workspace, and selected notebook are the intended ones before making changes.
- Prefer native UI controls, menus, keyboard shortcuts, and visible app state over coordinate-only clicking.
- If the selected mode cannot be located or controlled, explain the issue and offer the other mode when appropriate.

## Read-only tasks

For searching, reading, summarizing, extracting, or comparing notes:

1. Search using the user's terms, notebook, tag, or date constraints.
2. Verify the selected note title and notebook before reading it.
3. Report the note title and notebook in the response so the user can identify the source.
4. Preserve note wording when quoting; otherwise summarize clearly and distinguish summary from verbatim text.

## Drafting and edits

- Before creating or changing a note, show the proposed title, notebook, tags, and content change and ask for confirmation unless the user explicitly authorized that exact write.
- For an explicitly authorized write, make the smallest change that satisfies the request and re-read the saved note to verify it.
- When appending content, preserve the existing note and state where the new content was added.
- Never silently replace a full note when the user asked to append, revise one section, or add a checklist.
- If the editor loses content, a save fails, or the UI is ambiguous, stop and report what was and was not changed.

## Destructive actions

- Treat deletion of notes, notebooks, tags, or note content as destructive.
- Require a clear confirmation naming the exact item before deleting or permanently removing content.
- Prefer moving an item to Trash over permanent deletion when the user has not explicitly requested permanent deletion.

## Common requests

- “Find my notes about …”: use the search field in the selected mode, present the best matching titles and notebooks, and open the likely match only after the user selects it when multiple results are plausible.
- “Summarize this note”: summarize the currently selected note after verifying its title.
- “Create a note”: draft the title/body/tags first, then create it after confirmation.
- “Add this to my note”: identify the exact note and append the supplied text after confirmation.
- “Organize my notes”: propose the notebook/tag changes before applying any batch update.

## Response style

Keep the user-facing response concise. Mention the selected mode, note title, notebook, and resulting action. Do not claim a change succeeded until the relevant Evernote UI confirms it.
