Vault assistant
## Ground Rules
- Read-only by default. Never modify, rename, or delete files without explicit user confirmation.
- For any bulk operation, propose a plan first and wait for approval.
- Use grep/find to locate files before reading content. Do not load files speculatively.
- Skip `Daily Notes/` and `Templates/` unless explicitly instructed.
- Never touch `Templates/` under any circumstance.

## Vault Structure
Flat file structure by design. Do not suggest or create subdirectories.
Only 3 directories exist:
- `Daily Notes/` - ephemeral scratch pad, files should be empty. Non-empty = unprocessed inbox item.
- `Templates/` - never touch
- `Attachments/` - media files only

## Note Taxonomy
- **Evergreen**: atomic, single concept, evolving knowledge. Title is a full descriptive sentence.
- **Log**: time-based capture (with date). Embed logs in the parent note by default; only extract to a separate file when the log grows too large.
- **MOC**: birds-eye view linking related notes. No need for suffix, just the note name
- **Project**: time-bound, acts as MOC for related evergreen notes.

## Note Status Tags
- `#todo` - incomplete note
- `#archived` - completed/cancelled/inactive
- `#ongoing` - still in progress (e.g. ongoing sickness log)

## File Naming Conventions
### Log notes
Use `Log -` prefix only when "log" isn't already in the filename and there's no company prefix to scope it.

- `Log - 1-1 - <name>` (break into yearly if needed: `Log - 1-1 - <n> - yyyy`)
- `Log - Health - yyyy-mm-dd - <Child 1|Child 2> - <sickness>`
- `Log - Catch Up - <name>`
- `Log - Course - <course name>`
- `Log - Book - <book title>`
- `Log - <Project name>` (standalone side project logs only; prefer embedding in project note)
- Company-scoped logs use company prefix instead: `<COMPANY> - On Call Log`, `<COMPANY> - <topic> - yyyy-mm-dd`

### Evergreen note prefixes
- `Book - <title>` (final summary, not daily log)
- `Course - <title>` (final learnings)
- `Idea - <title>` (solidified, actionable idea)
- `<COMPANY> - <note title>` (company-specific notes)
- `Post - <title>` (published content)
- `Draft - <title>` (draft for publishing)
- `Prompt - <title>` (LLM prompts)
- `Story - <title>` (story bank for communication)

### Other
- `Speech - <title>`, `Letter - <title>`
- Root index/MOC files use emoji prefix (e.g. `🏡 Home`, `📥 Inbox`)
- MOC suffix only added when note is too large to fit all references cleanly

## Company Prefix Mapping
2-4 char ALL CAPS. Use exactly as listed.

ACME=ACME Corp, IND=Indeed, CFLT=Confluent, EYE=Eyeota

## Note Associations
- No tags or topics. Associations are explicit inline links or coarse-grained "See also" sections.
- Fine-grained links preferred: link in context of a sentence, not just a list of related notes.
- MOCs are the primary navigation structure.

## Confidentiality
- Files with `<COMPANY> -` prefix may contain client/employer sensitive content. Do not include their content in any summarised output unless explicitly asked.
