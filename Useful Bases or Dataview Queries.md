Bases (previously Dataview) queries used in my [[Obsidian]] vault with explanation. 

> [!NOTE] Dataview is only maintenance mode
> Since Dataview engineer hired by Obisdian, it is now in maintenance mode and with the new Obisdian Bases, there is no more need for Dataview. See Useful Bases queries for references

## [[📥 Inbox]]
### Unprocessed Daily Notes
Base:
```
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

Dataview:
```
TABLE file.size AS "Size (bytes)", (date(today) - file.mday).day as "Days since modified", file.tags AS Tags
WHERE regexmatch("^\d{4}-\d{2}-\d{2}$", file.name) AND file.size > 0
SORT file.name DESC
```

This shows the files that matches the regex (yyyy-mm-dd) and additional column to show how many days since it was last modified

### Todo
Base:
```
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

Dataview:
```
TABLE (date(today) - file.mday).day as "Days since modified", 
file.tags AS Tags
FROM #todo
WHERE !regexmatch("^\d{4}-\d{2}-\d{2}$", file.name) AND
file.name != "🏷 Tags"
SORT file.mtime DESC, file.name
```
This will show the list of files that has `#todo` tag and does not match daily notes (yyyy-mm-dd)

## [[📋 Kids Health Log]]
### Ongoing Kids Sickness
Base:
```
filters:
  and:
    - file.hasTag("ongoing")
    - /^Log - Health/.matches(file.name)
properties:
  file.name:
    displayName: File
views:
  - type: table
    name: Table
    order:
      - file.name
    sort:
      - property: file.name
        direction: DESC
```

Dataview:
```
LIST FROM #ongoing 
WHERE regexmatch("^Log - Health - .*$", file.name)
SORT file.name DESC
```
Straightforward query that queries based on `#ongoing` tag and matches the file name regex

### Past Records
Base:
```
filters:
  and:
    - !file.hasTag("ongoing")
    - /^Log - Health/.matches(file.name)
properties:
  file.name:
    displayName: File
views:
  - type: table
    name: Table
    order:
      - file.name
    sort:
      - property: file.name
        direction: DESC
```

Dataview:
```
LIST FROM -#ongoing
WHERE regexmatch("^Log - Health -.*$",file.name)
SORT file.name DESC
```
Straightforward query that queries based on `#ongoing` tag and matches the file name regex

## [[🥷 People]]
### Sorted by last update
Base:
```
formulas:
  name: file.asLink(file.name.replace("Log - People - ", ""))
  modified: today() - file.mtime
properties:
  formula.name:
    displayName: Name
  file.tags:
    displayName: Tags
  formula.modified:
    displayName: Last modified
filters:
      and:
        - /^Log - People - .*$/.matches(file.name)    
views:
  - type: table
    name: Table
    order:
      - formula.name
      - formula.modified
      - file.tags
    sort:
      - property: formula.modified
        direction: ASC
      - property: formula.name
        direction: ASC
    columnSize:
      formula.name: 311
```

Dataview:
```
TABLE WITHOUT ID link(replace(file.name, "Log - People - ", "")) AS Name, 
dur(string(max((date(today) - file.mday).day, 0)) + " days") AS "Since contacted", 
file.tags AS Tags
WHERE regexmatch("^Log - People - .*$", file.name)
SORT file.mday DESC, Name
```
This fetch the list of files starting with `Log - People - <name>` but it then links it to `<name>` directly.
It also shows the duration from since last contacted (based on `Log - People - <name>` modified timestamp)

## See also
- [[🤖 System]]
