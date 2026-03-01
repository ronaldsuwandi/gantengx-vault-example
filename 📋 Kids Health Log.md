## 📆 General Medicine Timeline

- Fever and cough - 3-4 days (afternoon gets better first, then morning and night. Phlegm is the last to go and can last longer)
- Diarrhoea - 3-4 days (give probiotic LBB2 after diarrhea 3x)
- Stomach pain - 1-2 days get better and vomit will stop and usually after vomit stop will be followed up by diarrhoea
- Morning and night phlegm last to go (1 week)
- Runny nose/flu - 1 week full drip (twice/day medicine) not better see a doctor
    - Nasonex only if prolonged because it has steroids. Usually 1 month spray can reduce
    - Xyzal usually 7 days should be ok
- The symptom usually double time (1 week cough - usually 2 weeks to resolve, 3-4 days usually - 1 week dosage)
- Cough
	- Symbicort tail off from 2-2, 1-2, 1-1, 0-1, 0 (1 week apart. Only if 1 week no cough completely then tail off). 
	- For Christian symbicort only start to tail off after one month no cough
	- Singulair one week reduce one much better

## 🤒 Ongoing Kids Sickness

```base
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

## 📋 Past Records
```button
name New Entry
type command
action QuickAdd: 📋 New Health Log
```

```base
filters:
  and:
    - '!file.hasTag("ongoing")'
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
