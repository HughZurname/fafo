# FAFO

**Fuck Around and Find Out. Build enough to learn. Keep what earns its place.**

![Roger Skaer demonstrating the rising relationship between fucking around and finding out](assets/fafo-graph.jpg)

*The graph that gave the project its name. [Meme source and credit](assets/README.md).*

FAFO is a small collection of agent skills for product development where understanding emerges through the work. Questions, experiments, implementation, and verification inform each other. The next action depends on what needs to be learned or delivered.

Generating code is cheap relative to understanding everything it leaves behind. Tests, abstractions, and specifications all consume attention. FAFO asks what each artifact contributes and keeps room to revise an early decision.

This is an initial working draft. The package has structural validation and an editorial review; behavioural effectiveness remains to be established in real sessions. See [evaluation cases](docs/evaluation.md).

## The skills

| Skill | Useful when | Result |
| --- | --- | --- |
| [fafo](skills/fafo/SKILL.md) | Work needs to move between discovery and delivery | A useful next action and continuity between modes |
| [fafo-clarify](skills/fafo-clarify/SKILL.md) | A consequential product decision is unclear | Enough shared understanding to proceed |
| [fafo-explore](skills/fafo-explore/SKILL.md) | Behaviour or solution shape needs investigation | An observation that changes a decision |
| [fafo-build](skills/fafo-build/SKILL.md) | Enough is understood to implement | A coherent, working increment |
| [fafo-verify](skills/fafo-verify/SKILL.md) | A claim needs evidence beyond a green suite | Focused evidence and explicit limits |
| [fafo-simplify](skills/fafo-simplify/SKILL.md) | Accumulated machinery obscures the work | Less complexity with required behaviour preserved |

Each skill stands alone. The main skill can coordinate the work, but installing it does not require the others. There is no prescribed sequence, compulsory interview, or mandatory specification handoff.

## Install

Clone [HughZurname/fafo](https://github.com/HughZurname/fafo), then copy the individual skills you want as described below. The repository also contains Codex and Claude Code plugin manifests pointing at the same skill directory. The manifests have not yet been exercised in both hosts.

## Use locally

Copy the folders you want from `skills/` into the skill directory supported by your agent. Each folder contains a standard `SKILL.md` with a name and description. No runtime dependencies, custom commands, or external services are required by this package.

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

## Principles

### Understanding is provisional

A product's needs and a solution's shape can become clearer during implementation. Questions and executable experiments expose assumptions. A note or test can capture an understanding without making it irreversible.

### Evidence must be able to disagree

Generated tests can inherit the assumptions of generated code. Confidence improves when expected results come from user-grounded examples, domain rules, independent calculations, or external contracts. A real integration exercise supports a different claim from a test against mocked collaborators.

### Artifacts have an ongoing cost

A test earns its maintenance cost by detecting a meaningful failure. An abstraction earns its place by expressing a real responsibility. A document earns its place by preserving consequential understanding. There are no universal quotas.

### A steel thread anchors the system

A steel thread is a narrow working path from an initiating action through the necessary components to a useful result. It exposes integration assumptions. Its happy path is an anchor; consequential rejection, retry, and partial-failure behaviour still need attention.

### Handoffs preserve momentum

A useful handoff carries the current outcome, evidence, decisions, important unknowns, and the next action. Existing conversations or project records often suffice. Returning to exploration after implementation reveals something new is ordinary progress.

## Scope

FAFO is aimed at ordinary product development. It makes no safety-critical assurance claim and supplies no certification process. Verification still scales with the consequences of the change, including data integrity, security, accessibility, and compatibility.

Test-first development, short specifications, unit tests, and mocks remain available where useful. FAFO does not prescribe their timing or treat them as universal prerequisites. Existing project requirements and the user's explicit choices still apply.

## Examples and improvement

Read [a worked development story](docs/example.md) to see movement between capabilities. Use [the evaluation cases](docs/evaluation.md) to probe whether a skill makes useful decisions before expanding its instructions.

For a proposed change, provide a real request, the observed failure, and why the proposed instruction would improve that decision. Prefer a narrow correction over a new universal prohibition. Do not include credentials, private customer data, or proprietary source in public examples.

## Inspiration

- [Matt Pocock's skills](https://github.com/mattpocock/skills): focused questioning, modular capabilities, and experiments that answer concrete questions.
- [Ponytail](https://github.com/dietrichgebert/ponytail): reuse, restraint, and reducing unnecessary implementation machinery.

The initial draft was informed by locally installed versions of their grilling, prototype, TDD, and Ponytail skills, inspected in September 2026. Those copies may differ from current upstream versions. FAFO's skill text is newly written; neither project is a dependency or an endorser.

## License

Original skill text and documentation: [MIT](LICENSE). The sourced meme image is excluded; see [asset provenance](assets/README.md).
