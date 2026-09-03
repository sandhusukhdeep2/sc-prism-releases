# SC Prism

**Control over the AI you run. Not a promise — a record.**

SC Prism is a governance and orchestration platform for people who want to run
many AI agents and still know exactly what they did. Multiple models work one
shared board, deterministic code decides who acts, every action lands on an
auditable record, and your own tests — not the model that did the work — decide
whether it counts as done.

It ships today as a single macOS app for one person. That is the first step of
a deliberate sequence, not the shape of the thing.

![SC Prism — a project room with its staffed crew](assets/hero.png)

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/how-it-works-dark.svg">
  <img alt="How one run works: you ask; a deterministic orchestrator staffs a crew with each seat on its own AI; every tool call passes your grant, the agent's own definition and a destructive-command denylist; the work is verified by your own tests at zero tokens before any AI judge; the result is a verdict with replayable hash-chained evidence. A privacy floor evaluated before every routing decision pins credential-bearing text to the local model." src="assets/how-it-works-light.svg">
</picture>

---

## The bet

**The harness — not the model — decides whether you can depend on what ships.**

Every serious tool now fans work out across agents, so "many agents" is
commoditising fast. What is not commoditising is being able to prove what they
did: a verifier that runs your own checks first, an audit trail you can replay,
routing that keeps sensitive work on your machine, and models that get cheaper
as they learn from verdicts rather than from vibes.

*Provably done, on-prem, at falling cost.*

## Where this came from

SC Prism is the third form of an idea. The first, **OpenLux**, hit a dead end
worth naming: a primary AI controlling other AIs. It fails because the thing
you most need to trust — who decides, in what order, with what permission — is
delegated to the least predictable component in the system.

SC Prism inverts it. A deterministic orchestrator controls the models; a model
never controls models. Everything else follows from that one decision.

## What "control" actually means here

Six things, each enforced rather than promised:

- **You decide what each agent may touch.** Capabilities are granted per agent,
  declared in the agent's own file, and gated at the moment of the call — not
  configured once and forgotten.
- **Sensitive work cannot leave.** A routing floor pins credential-bearing text
  to your local model, and it is evaluated *before* any routing decision, so no
  budget, preference or convenience can override it.
- **Every action is on the record.** Which agent, on which model, ran which
  command, read which file, with what result — hash-chained, replayable, and
  written whether or not anyone is watching.
- **Done is decided by your tests.** A deterministic gate runs first at zero
  token cost. Only work that survives it reaches an AI judge.
- **Many models, one board.** Claude, Gemini and models on your own hardware
  take different seats on the same task, and the record shows who did what.
- **Your knowledge is yours.** Agents, skills, projects and verdicts are plain
  markdown in one folder. Readable in Obsidian, diffable in git, portable to
  any machine — and to other tools, because the formats are open standards.

## Open standards, one per layer

Vendor-neutral by construction, which is the direct answer to lock-in:

| Layer | Standard | What it connects |
|---|---|---|
| Tools | **MCP** | agents to external tools and services |
| Agents | **A2A** | agents to each other |
| Knowledge | **OKF** | your vault to any consumer |
| Capabilities | **Agent Skills** | reusable procedures to any agent |

A skill written elsewhere works here; one written here works elsewhere. Your
knowledge and capabilities are portable on day one, not after an export.

## Who it is for

**Solo builders** who want a crew without giving up oversight — and who would
rather see a refusal than a plausible answer.

**Teams and enterprises** who need AI work to be attributable, permissioned and
auditable before it can be adopted at all. The governance model — distinct
identity per agent, role and attribute based access, least privilege bound to
the moment and expired after — is the product, not a setting inside it.

The solo app is first because it is the honest way to prove the core: the
founder is user number one, and SC Prism builds SC Prism.

---

## Why this exists

AI tools ask you to trust a black box. SC Prism is built on the opposite bet:

- **A model never orchestrates models.** Deterministic code chairs every
  multi-agent run. Agents contribute; the machinery decides whose turn it is.
- **Done is proven where there is something to prove.** When a run is bound to
  a project, a deterministic gate runs first — your tests, lint and build, at
  zero tokens — and a failure there short-circuits before any judge spends a
  token. When there is nothing to compile, the gate says so out loud
  (*"skipped — nothing was checked"*) instead of showing a tick it did not
  earn. A failed check is shown as a failure, in red, with the reason.
- **Privacy has a floor.** A keyword gate scans every message and every tool
  result before it can leave the machine. Text carrying `password`,
  `credential`, `api-key`, `token`, `secret` and the terms you add yourself is
  pinned to your local model and cannot go to the cloud — even when you
  explicitly ask for cloud. It is a word-level gate, not a content classifier:
  on its own it will not recognise an unlabelled API key, an account number or
  a home address. For work that must never leave the machine, set the
  dependency dial to **Local first**.
- **Everything is a file you own.** Agents, skills, projects, verdicts, and
  reports are plain markdown in one vault folder — readable in Obsidian,
  diffable in git, portable anywhere. Nothing is locked inside the app.

## What you can watch it do

When you send a task, the chat shows the work happening — live, attributed,
and real:

- **Every seat speaks for itself.** Each agent's contribution appears as its
  own bubble — agent name · AI brand · board turn — with the manager's
  synthesis labeled as exactly that.
- **Every action is on the record.** The live stream shows each file added or
  updated by name, each terminal command with its exit code, each web search
  with its query, each vault file read — every row expandable into honest
  IN/OUT detail. Nothing summarized away, nothing invented.
- **Governance is part of the story.** A blocked call shows ⛔ with the rule
  that blocked it. A sensitive result fetched from the web but withheld from
  the cloud shows 🔒. Held actions say they're waiting for your approval.

## The capability system — real power, three locks each

Agents can research the web, control the computer (screenshots, opening
apps), and run terminal commands — for real jobs: builds, 3D pipelines,
whatever a terminal can do. Every capability sits behind three locks:

1. **Your grant** — computer and terminal access never default on.
2. **The agent's own definition** — a seat only holds a tool its own file
   declares.
3. **The approval gate** — every acting tool stops for your yes the first
   time. Approve it once and it stays granted until you revoke it in
   `<vault>/mcp-approvals.json`. What ran is what is recorded: command,
   folder, exit code.

## One vault, everything in it

Your chosen folder (an Obsidian vault works) holds the whole company: agent
definitions, skills, every project and its files, every verdict with its
hash-chained evidence, every report. Open it in any editor. Take it to any
machine.

The app includes its own project workspace too — a file tree per project,
edit-and-save with a diff gutter, one-click preview of any HTML page or image
in your default apps.

## Cost, honestly

A dependency dial (Local first · Balanced · Online first) sets how much work
leaves your Mac. The ledger derives every number from recorded runs — the
local-share percentage and today's cloud spend come from the same records the
run history shows, structurally incapable of disagreeing with it.

## Safety, described exactly

Three independent layers stand between a model and your machine. Each is
described here as what it is, not as what would sound best.

**1. Grants.** Computer and terminal access are off until you turn them on,
and an agent only holds a tool its own definition file declares. Both must
agree.

**2. A destructive-command denylist.** Every shell command is scanned before
it executes. `rm -rf ~`, `mkfs`, `dd of=/dev/…`, fork bombs, `git reset
--hard`, `curl … | sh` and their relatives are refused outright, and the
refusal is recorded. The list is deliberately narrow: `rm -f build/tmp.o`,
`git push --force-with-lease` and `grep -r reboot .` all run normally, because
a guard that blocks ordinary work teaches you to switch it off.

**3. Containment — a deny-list, not a sandbox.** Commands run through macOS
`sandbox-exec` with two things closed: your saved credentials are unreadable
(the app's own key store, `~/.ssh`, `~/.aws`, keychains), and SC Prism's own
approval file is unwritable, so a command cannot approve itself for future
tools.

**What containment does not do**, stated plainly: the command still runs as
your user. It can read and write your ordinary files, reach the network, and
use your installed tools. Verification commands you configure run outside the
containment. If `sandbox-exec` is unavailable, the command runs uncontained
and the record says `contained: false` — the trace never claims a protection
that was not applied.

## Proven, not claimed

Every subsystem is probed against the shipped bundle before release — not
mocked, not described. The most recent pass, run against this build:

```
PASS  denylist refuses rm -rf ~          destructive command blocked pre-exec
PASS  containment hides API keys         unreadable
PASS  containment blocks self-approval   approvals intact
PASS  ordinary commands run              unaffected
PASS  web search returns results         real results
PASS  vault tools work                   readable
PASS  skills catalog loads               4 skills
PASS  vault recall (BM25)                3 docs in 44ms
PASS  skill allowed-tools narrows        narrowed, source untouched
PASS  manifest refuses wildcards         refused
PASS  confidential forces local          pinned to this machine
PASS  scope approval is inert            approving scope grants nothing
PASS  audit catches aliased eval         AST, not regex
PASS  sandbox-exec available             Gate 2 enforceable
```

These passes are the product of finding real failures, not of avoiding them.
A partial list of defects this discipline caught and fixed: an agent whose
definition asked for the web was silently denied it; keyless web search
returned nothing while looking functional; two concurrent runs could fork the
audit chain; a subscription bridge pasted the app's own system prompt into the
user turn, so the model refused it as an injection attempt; a timeout claimed
to kill a command's children and did not; a five-minute cap discarded
everything a run had accomplished instead of reporting it; and the eval gate
returned success whether or not it had blocked.

Each one is now covered by a test that fails without the fix.

## Agent Skills — the open standard

A skill is a folder with a `SKILL.md` describing a procedure, and SC Prism
reads and writes the open [Agent Skills](https://agentskills.io) format. A
skill written for another tool works here; one written here works elsewhere.

Skills load progressively, in three tiers: the name and description at
startup, the full procedure when a task matches it, and bundled reference
files only when the procedure actually cites them — so a skill can carry a
large reference that costs nothing until it is needed.

A skill may also declare `allowed-tools`. That declaration can only ever
*narrow* what an agent may do on a turn, never widen it: importing a skill can
never grant a capability you did not.

## Memory that reads whole documents

Recall ranks your vault with Okapi BM25 over the full text of every note, then
reranks the shortlist. A decision recorded in a note's third paragraph is
findable; it does not have to be in the title. On a 70-file vault a query
returns in about 20 milliseconds, entirely on your machine, with no embedding
service and no vector database.

## Where this is going

Stated as a direction, not a promise, and separated from what ships today.

**This release** is the solo application: one person, one machine, a full crew,
on macOS.

**Designed for and not yet built:** cross-platform desktop; a team mode where
colleagues connect to a gateway you host and run under your governance without
ever holding your keys; an editor surface with routing and the vault built in
rather than bolted on; a governance console for spend, drift and audit across a
team; and a training loop that improves local models from recorded verdicts, so
capability rises while cost falls.

The architecture already assumes all of it. The engine is Python, the router is
Go, the surface is web technology, agent-to-agent seams are in place, and the
vault is a portable open-format bundle. None of that is load-bearing on macOS.

What separates this from a roadmap is the rule the whole product runs on: a
thing is described as built only when it can be demonstrated. Everything above
is honestly labelled as not yet there.

## Status: solo alpha

One person, one Mac, full crew. Built by a solo founder, and it dogfoods
itself — parts of SC Prism's own tooling were built by SC Prism's crew, on the
record.

## Install

1. Download `SC.Prism.dmg` from the [latest release](../../releases/latest).
2. Open it, drag **SC Prism** to Applications, launch.
3. The setup wizard walks you through providers (your own Claude/Gemini
   accounts or API keys, and/or a local model server), your vault folder, and
   the grants you choose to give.

**Website:** [sandhusukhdeep2.github.io/sc-prism-releases](https://sandhusukhdeep2.github.io/sc-prism-releases)

**Requirements today:** macOS 14+ (Apple Silicon). macOS is where this starts, not where it stops — the engine is Python, the router is Go, and the surface is web technology, so nothing in the architecture is tied to one platform. Cross-platform follows the solo core being proven. Bring your own AI: a Claude or
ChatGPT subscription CLI, API keys, and/or a local OpenAI-compatible model
server (e.g. an MLX host). The app ships with no keys and phones home to no
one.

## Privacy

No telemetry, no analytics, no accounts. Keys are held by the app's gateway
and never rendered. The only network calls are the ones your runs make to the
providers you configured — and the record shows every one.

---

*SC Prism is independent software. It is not affiliated with Anthropic,
Google, OpenAI, or the Obsidian project.*
