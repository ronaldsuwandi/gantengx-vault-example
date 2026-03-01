Bunch of ideas to start my side project/income

## 💡 Ideas to explore
```base
filters:
  and:
    - '!file.hasTag("archived")'
    - /^Idea -/.matches(file.name)
properties:
  file.name:
    displayName: File
views:
  - type: table
    name: Table
    order:
      - file.name
    sort:
      - property: file.mtime
        direction: ASC
    cardSize: 150

```

## 🗃 Archived/cancelled
```base
filters:
  and:
    - 'file.hasTag("archived")'
    - /^Idea -/.matches(file.name)
properties:
  file.name:
    displayName: File
views:
  - type: table
    name: Table
    order:
      - file.name
    sort:
      - property: file.mtime
        direction: ASC
    cardSize: 150

```

## 💨 Ongoing
Ongoing ideas that's approved and ongoing 🟢
- 

## ✅ Completed
This is the list of actual ideas that converted into project and completed/archived
- [[Oh Yah!]]
- [[chessterm]]
