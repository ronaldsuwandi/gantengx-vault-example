This inbox page contains the things that needs to be processed. It's basically split into two parts:
1. Daily notes that matches the regex (yyyy-mm-dd) and have size more than 0 bytes. This means that there is a content in the file that needs to be processed
2. Non-daily notes that has `#todo` tag attached to them, sorted by last modified date in descending order

## 📆 Unprocessed Daily Notes
```base
formulas:
  modified: today() - file.mtime
properties:
  file.tags:
    displayName: Tags
  file.name:
    displayName: File
  file.size:
    displayName: Size (bytes)
  formula.modified:
    displayName: Last modified
filters:
  and:
	- /^\d{4}-\d{2}-\d{2}$/.matches(file.name)
	- file.size > 0    
views:
  - type: table
    name: Table
    order:
      - file.name
      - file.size
      - formula.modified
      - file.tags
    sort:
      - property: file.name
        direction: DESC
    columnSize:
      file.name: 230
      file.size: 128
      formula.modified: 193

```

## 📋 Todo
```base
formulas:
  modified: today() - file.mtime
properties:
  file.name:
    displayName: File
  file.tags:
    displayName: Tags
  formula.modified:
    displayName: Last modified
filters:
  and:
	- "!/^\\d{4}-\\d{2}-\\d{2}$/.matches(file.name)"
	- file.name != "Tags"
	- file.name != "Post - The PKM Setup I Settled On After Many Iterations"
	- file.hasTag("todo")
views:
  - type: table
    name: Table
    order:
      - file.name
      - formula.modified
      - file.tags
    sort:
      - property: file.name
        direction: ASC
      - property: formula.modified
        direction: ASC
    columnSize:
      file.name: 364

```
