Note templates are stored in `Templates/` directory and generally I only have few templates to keep ceremony as minimum as possible

## Evergreen notes
Default note with minimal template overhead. Generally contains 2 headers and basic 4 buckets

```
<main body>

## Facts
- points

## Procedural
- points

## Conceptual
- points

## Questions
- points

## See also // optional
- point to page that has related concepts

## References // optional
- <any url/references>
```

## Project
Any time-bound notes like learning, course, training, projects

```
Date: <start date> - <end date>
Due: <date> // optional
Goal: <goal of project> // optional

---

<main body describing the nature of the project>

## See also
- point to the evergreen note about the concept (e.g. if this is about Kafka certification, point to Kafka notes and the learnings)
- point to log about the project if exists
- point to other page that has related concepts

## References // optional
- <any url/references>
```

## Area
Area/resource about any ongoing focus/interest area. This should be similar to [[#Evergreen notes]] or can be [[#MOC]]

```
<main body describing the nature of the area>

## See also
- point to other page that has related concepts
```

or it could also be reference/source note

```
Date: <date note was written>
Author: <author name>
Source: <source>

---

<summarised note>

## See also
- point to the evergreen note about the concept (e.g. if this is about Kafka certification, point to Kafka notes and the learnings)
- point to log about the project if exists
- point to other page that has related concepts

```

## MOC
Generally used for birds eye view/high level overview to group related concepts together

```
<optional summary of the MOC>

## Grouping 1
- link to page
- link to other page

## Grouping 2
- link to other page

## See also // optional
- point to other related page if exists

## References // optional
- point to url/reference if exists
```

## Log
Log-based generally ephemeral and temporary but some log note can be converted to [[#Evergreen notes]] if there is a need to it. Alternatively I can also have the [[#Evergreen notes]] version of the topic and have a link to the log to capture the thought trails

Generally grouped by date, ideally have a short single liner summary on the date so that when the dates are all collapsed I can still have a quick at a glance view on what was the most important thing captured on that day instead of simply showing date

```
<optional summary of the log>

## 2023-02-21
- something to note here

## 2023-02-19: this date I found the way to fix the bug
- point found
- another point found

## See also // optional
- point to other related page if exists

## References // optional
- point to url/reference if exists
```

For [[📋 Kids Health Log]] it's slightly different, it has its own template

```
#ongoing // if still sick
## 2023-02-06
- Morning: medicine
- Afternoon: 
- Evening: medicine

## 2023-02-05: cough improving
...
```

## Archived
Any note with `#archived` tag attached to it (first line in the note)

```
#archived
<some notes>
```

## Scratching pad
Either in daily note format, without any specific template OR in any note and have `#todo` tag attached to it

```
<daily note>

## Facts
- points

## Procedural
- points

## Conceptual
- points

## Questions
- points

```

or 

```
#todo
<some note that's incomplete and need to be further processed>

## Facts
- points

## Procedural
- points

## Conceptual
- points

## Questions
- points

```

or 

```
<some note>
<some points that needs to be addressed> #todo

## Facts
- points

## Procedural
- points

## Conceptual
- points

## Questions
- points

```


## Person
It's a shortcut to create a new person with simple base query to keep track when was the last time I update note about the person
```

## Logs
- [[Log - People - <name>]]
```
