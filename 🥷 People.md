This is where I keep info about people that I interacted with and have **importance** in my life. Person can be in [[👥 1-1s]] but doesn't necessarily mean it should come under this page due to importance

```button
name New Person 🙃
type command
action QuickAdd: 🙃 New Person
```

## Family and Friends
### Family
- [[Child 1]]
- [[Child 2]]
### Friends
- [[Friend 1]]

## By Eras
### ACME
- [[Manager 1]]
- [[Lead 1]]
### Indeed
- 
### Eyeota
- 

## Special Areas
### Important Recruiters
- [[Recruiter 1]]

## Sorted by last update
```base
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

## See also
- [[👥 1-1s]]
