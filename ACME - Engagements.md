[[ACME - Pre-engagement checklist]]

Engagements

```base
properties:
  file.name:
    displayName: File
filters:
  and:
	- file.name.startsWith("ACME - Engagement -")
views:
  - type: table
    name: Table
    sort:
      - property: file.name
        direction: ASC

```
