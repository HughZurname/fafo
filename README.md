# FAFO

Fuck Around and Find Out.

Agent skills for exploring a problem, building a solution, and finding out whether it works.

![Roger Skaer demonstrating the rising relationship between fucking around and finding out](assets/fafo-graph.jpg)

*The graph that gave the project its name. [Meme source and credit](assets/README.md).*

FAFO is a collection of agent skills for figuring out what you're building as you build it. Ask questions, try things in a REPL, get a path through the system working, and revisit the approach when you learn something new.

An agent can generate a huge test suite before you've worked out whether its assumptions make sense. Someone then has to read and maintain it. FAFO puts that cost into the decision: what does this test, abstraction, or document help us understand or protect?

This first draft has passed structural checks and an editorial review. It still needs use in real development sessions. The [evaluation cases](docs/evaluation.md) describe how to assess it.

## The skills

| Skill | Useful when | Result |
| --- | --- | --- |
| [fafo](skills/fafo/SKILL.md) | Work needs to move between discovery and delivery | A next action that fits what is known |
| [fafo-clarify](skills/fafo-clarify/SKILL.md) | A product decision is holding up the work | Enough shared understanding to proceed |
| [fafo-explore](skills/fafo-explore/SKILL.md) | You need to see how something behaves | An observation that changes a decision |
| [fafo-build](skills/fafo-build/SKILL.md) | Enough is understood to implement | A working piece of the product |
| [fafo-verify](skills/fafo-verify/SKILL.md) | Passing tests leave an important question unanswered | Evidence of what works and what remains unchecked |
| [fafo-simplify](skills/fafo-simplify/SKILL.md) | Code or tests have become harder to understand than they need to be | Less complexity with required behaviour preserved |

Install the skills you want. Each works on its own, and the main skill can help choose between activities without needing its companions installed. You can move between them as needed. A clear task can go straight to implementation; an unfamiliar one may need questions or experiments first.

## Install

Install from [HughZurname/fafo](https://github.com/HughZurname/fafo) with the [Skills CLI](https://skills.sh/docs/cli):

```sh
npx skills add HughZurname/fafo
```

Choose the skills and agent in the installer's prompts. To inspect the available skills without installing:

```sh
npx skills add HughZurname/fafo --list
```

For an individual skill:

```sh
npx skills add HughZurname/fafo --skill fafo-explore
```

You can also clone the repository and copy the folders as described below. Codex and Claude Code plugin manifests point to the same skill directory. Installation through both hosts still needs checking.

The [skills.sh FAQ](https://skills.sh/docs/faq) explains that directory listings and rankings come from installation telemetry. Hosting a repository makes it installable; it does not guarantee immediate directory visibility.

## Use locally

Copy the folders you want from `skills/` into the skill directory supported by your agent. Each folder contains a standard `SKILL.md` with a name and description. The package needs no runtime dependencies, custom commands, or external services.

For Codex, copy selected folders into `~/.codex/skills/`, keeping the folder names. For example, from this repository:

```sh
mkdir -p ~/.codex/skills
cp -R skills/fafo-explore ~/.codex/skills/
```

Check for an existing folder with the same name before copying. Start a new task if the host does not refresh its skill list automatically. Other agents may use a different discovery directory or invocation syntax; use their supported skill mechanism.

Example requests in a host that supports `$skill-name` invocation:

- “Use $fafo to work through this feature and build it. We can revise the approach as we learn.”
- “Use $fafo-clarify to help me decide what duplicate uploads should mean.”
- “Use $fafo-explore to establish what happens when a request is retried.”
- “Use $fafo-verify to assess whether this green suite demonstrates the intended outcome.”
- “Use $fafo-simplify to reduce the complexity of this module while preserving its behaviour.”

The descriptions allow normal discovery; actual automatic selection depends on the host. Installing FAFO does not disable other installed skills or resolve conflicts with their rules.

## How we approach the work

### Leave room to change your mind

Requirements often take shape during development. A question or a small experiment can expose something the original plan missed. Keep the current understanding in notes or tests when that helps, and revise it when the evidence changes.

### Give tests something independent to check

A model can put the same mistake in the code and its tests. Expected results need a separate basis: an example grounded in the user's intent, a domain rule, a worked calculation, or an external contract. Testing against a mock tells you less about integration than exercising the real components.

### Account for what you leave behind

Every test needs a failure it can detect. Abstractions should explain responsibilities in the code, and documentation should preserve something worth knowing. Fixed quotas for any of these miss the point: their benefit has to justify the time spent understanding and maintaining them.

### Get a steel thread working

A steel thread is a narrow path from an initiating action, through the components it depends on, to a useful result. It exposes assumptions about how the pieces fit together. Once it works, check the failures that matter too, such as a rejected request, a retry, or an operation that stops halfway through.

### Hand over what you know

The next person or session needs the current outcome, the evidence, decisions and their reasons, important unknowns, and a sensible next action. An existing conversation or project record is often enough. If implementation reveals a new problem, go back and investigate it.

## Show the thing you're trying to understand

A diagram can make an assumption easier to question. A sequence diagram might reveal where a retry repeats work; a before-and-after view can show whether an architecture change removes complexity or just moves it.

FAFO uses the conversation's visual capabilities when available. Static relationships may need only a Mermaid diagram or a table. A stateful interaction can justify an interactive view. The host determines what can be displayed, with text sketches as a fallback. A separate HTML report is useful when someone needs to share or keep it, but is not required.

Visuals distinguish what has been observed from what is assumed or proposed. A convincing simulation is still a simulation until its behaviour has been checked against the real system.

See [a visual clarification example](docs/visual-exploration.md).

## Scope

FAFO is for ordinary product development. It provides no certification process or assurance for safety-critical systems. The amount of verification still depends on what could go wrong, including damage to data, security failures, accessibility problems, and broken compatibility.

Use test-first development, a short specification, unit tests, or mocks when they help. Their timing depends on the work. Follow the project's requirements and the user's explicit choices.

## Examples and improvement

The [worked development story](docs/example.md) follows a retry bug through clarification, experiments, and implementation. The [evaluation cases](docs/evaluation.md) cover decisions the skills should handle before we add more instructions.

When proposing a change, show the request and what went wrong. Explain how the change would have helped. Keep the fix specific to the failure, and keep credentials, private customer data, and proprietary source out of public examples.

## Inspiration

- [Matt Pocock's skills](https://github.com/mattpocock/skills): questions that challenge an idea and small experiments that help settle it.
- [Ponytail](https://github.com/dietrichgebert/ponytail): checking what already exists and writing less code when it will do the job.

The starting references were locally installed copies of their grilling, prototype, TDD, and Ponytail skills, read in September 2026. Those copies may differ from the latest upstream versions. We wrote FAFO's skill text from scratch. Neither project is a dependency, and neither has endorsed FAFO.

## License

Original skill text and documentation: [MIT](LICENSE). The sourced meme image is excluded; see [asset provenance](assets/README.md).
