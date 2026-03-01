I want the file names to be consistent, hence need to follow some sort of rules
- Generally main root index have emoji to keep it pretty (e.g. [[🏡 Home]], [[📚 Topics]], etc)
- No prefix for [[🤖 System#MOC (Maps of Content)|MOC (Maps of Content)]] and project notes. I initially thought it's useful to have MOC suffix for large note (e.g. Kafka) but I realised that I know myself that Kafka is a huge topic, so having MOC is really adding unnecessary ceremony
- Log-based notes (with date) will have `Log - <type>` prefix. *Some logs* are ephemeral and serve to capture the progress, for these kind of notes, once it's fully captured I can consider removing them and just create a proper evergreen note. Important to **avoid** log prefix for company notes to keep prefix simple (exception of 1-1)
	- `Log - 1-1 - <name>` for 1:1. If I have the same 1:1 person for 10 years, it's going to be big... Maybe can break this into yearly if needed - unlikely to be honest
	- `Log - Health - <yyyy-mm-dd> - <Christian|Matthew> - <illness>` 
	- `Log - People - <name>` for catching up
	- `Log - <Project name>` for any side project logs (prefer embedded if possible)
- Generally keep log embedded (be it for project, idea, engagements, etc) as much as possible and only extract when there is a need (log gets too large)
- Some of the [[🤖 System#Evergreen Notes|Evergreen Notes]] have prefixes. Otherwise generally it's a full sentence like [[Kafka message delivery semantics]] or [[IND - How to get an id of a job in intlaq evaluator service]]
	- `Book - <book title>` for book summaries
	- `Course - <course name>` for the final learnings
	- `Idea - <idea>` once the idea is solidified and is actionable
	- `<Company name> - <note title>` for any notes that is specific to company (e.g. `Indeed`, `Confluent`, `Eyeota`, etc). See [[Work file prefix mapping]] for the mapping (company name is shortened: IND for Indeed, EYE for Eyeota, etc)
		- This also applies to company-specific area (e.g. `EYE - Uni`, `IND - IQL`,  `KRUX - Data Sentry`)
		- Same with project/meeting notes (e.g. `IND - Intlaq Catchup`)
		- Also for engagement (e.g. `CFLT - Engagement - <customer>`) this will be project-note
	- `Post - <note title>` for public note in blog or other publishing platform I use
	- `Prompt - <prompt title>` for keeping track of [[LLM]] prompts
	- `Story - <story title>` for my story bank. Used for [[Communication]] (see: [[Storytelling formula]])
	- `Draft - <note title>` for draft public note
- As for [[💡 Ideas]], as mentioned before, can be prefixed with ideas prefix as I explore/research and have log attached to it
	- When the idea matures and converted into an actual project, then remove the idea prefix ([[wearther]] is an example)
- Non-evergreen notes related like letter, speech, etc
	- `Speech - <title>` for speeches (e.g. Yosep's wedding speech)
	- `Letter - <title>` letters 
- Specific to work related notes see [[Work file prefix mapping]]

## Logs
### [[2026-02-26]]
- Redo log type to drop ideas, books and course. Log for ideas is pointless because once the idea is promoted, then it can use Log for project (or embedded until necessary)

### [[2026-02-25]]
- Dropped MOC and project note prefix, removed stale log format for engagement
