## Facts
- Skills are lightweight open format to extend AI agent capabilities
- Format is markdown with YAML frontmatter
```yaml
---
name: analyze-marketing-campaign
description: Analyze weekly marketing campaign performance data across channels. Use when analyzing multi channel digital marketing data to calculate funnel metrics and compare to benchmarks, compute cost and revenue efficiency metrics, or get budget reallocation recommendations based on performance rules
---
<skill content>
```
- The name and description are required and used by the [[LLM]] agent to decide whether or not to use the skills
- Frontmatter constraints
	- Name
		- Max 64 chars
		- Only lowercase letters, numbers and hypens. Do not start or end with hypens
		- Must match parent directory name
		- Recommended: gerund (verb + -ing) form
	- Description
		- Max 1024 chars
		- Non empty
		- Should describe what the skill does and when to use it
		- Should include specific keywords that help agents identify relevant tasks
	- License (optional): path to license file
- Skill can load scripts and reference to other files
- [[Claude AI]]'s Prebuilt skills
	- https://github.com/anthropics/skills
- Skill body content
	- No format restriction
	- Recommended sections
		- Step by step instructions
		- Input, output format, examples of input/output
		- Common edge cases
	- Practical guidelines
		- **Keep it under 500 lines**
		- Move detailed reference material to separate files
			- Show basic content, link to advanced or domain specific content
		- Keep references one level deep from SKILL.md file (avoid nested file references)
		- Be clear and concise, use consistent terminology
		- Use forward slashes in file paths even on Windows

## Procedural
- To manage context size, skills are progressively disclosed
- When skills are loaded to the system, only metadata is loaded (name and description) and the content of the skills are only included when the AI decide to use them. This help manages the context size
- Subagent behave slightly differently with skills, when skills are loaded from subagent, the whole skill is loaded and not just the metadata
- Skills are typically stored under `SKILLS` directory. The structure is usually
	- skill-name/
		- SKILL.md
		- references/
			- additional documentation agents can read when needed
			- keep individual reference files focused
			- if reference file longer than 100 lines, have a TOC at the top will help agent to see the full scope
		- scripts/
			- python/bash/node script
			- scripts must have clear documentation
			- error handling is explicit and helpful
			- make it clear whether the agent should **execute** the script or **read** it as reference
		- assets/
			- doc/config templates
			- images: diagrams, logo
			- data files: lookup tables, schema

## Conceptual
- Skillls are very useful for **repetitive** task that requires context
- Example use case of agent skills
	- Domain expertise
		- Brand guidelines and templates
		- Legal review process
		- Data analysis methodologies
	- Repeatable workflow
		- Weekly marketing campaign review
		- Customer call prep workflow
		- Quarterly business review
	- New capabilities
		- Generate presentations
		- Generate Excel sheets or PDF reports
		- Building MCP server
- Without skills the same flow will require
	- Describe instructions and requirements everytime
	- Bundle all references and supporting files every time
	- Ensure workflow or outputs are always consistent
- Skills vs MCP
	- MCP conntect agent to external systems and data
	- Skill teaches agent what to do with the data
		- Essentially leveraging the result from MCP
- Skills vs Tools
	- Tools are lower level (e.g. read, write ,edit file, glob, grep, task, etc).
	- Tools propvide agents with capabilities to accomplish the tasks
	- Tool definitions are always live in the context window
	- Skill extends the agents with sepcialized knowledge
	- Skills can include scripts as tool that are used when needed (tools on demand)
- Skills vs Subagents
	- Subagent spawned and report back to the parent agent
	- Subagent have their own **isolated context** and tool permissions
	- Agent can delegate task to specialisedc subagent and work independently and return resultrs
	- Skills can provide expertise knowledge to the main agent or any of the subagents
- Example a Customer Insight Analyzer system
	- Skills: guide how to categorize feedback and how to summarise findings
	- Tools: MCP server to read customer interview notes and survey responses
	- Subagents: interview analyzer, survey analyzer
![[Pasted image 20260216155431.png]]

![[Pasted image 20260216155412.png]]
- When creating skills
	- Degrees of freedom
		- High: general text-based direction, multiple approaches are valid
		- Medium: instructions contain pseudocode, code examples or pattern. A preferred pattern exists but some variation is acceptable
		- Low: instructions refer to specific scripts and a sepcific sequence must be followed
	- Complex workflows
		- Break complex operations into clear, sequential steps
		- If workflows beocme large with many steps, consider pushing them into separate files

## See also
- [[LLM Skills]]
- [[LLM Preferences]]
- [[Prompt - Claude Code Prompt for Plan Mode]]

## References
- https://github.com/anthropics/skills
- https://skills.sh
- https://github.com/https-deeplearning-ai/sc-agent-skills-files/

