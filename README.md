<!--
  brew(doppio):

    git cherry-pick                 # it starts as a cherry, picked by hand
    git rebase single-origin        # one base. a blend would be a merge
    echo "*.sugar" >> .gitignore
    git commit -S -m "25s, 9 bars"  # signed, always

  Two espressos side by side would be a merge.
  A doppio is one extraction through a double basket.
  Linear history. One commit. No conflicts.
-->

# ☕️ caffe-doppio

`$ whoami`
 **systems thinker.** Developer, working where application code, data engineering
 and data governance meet.

> [!TIP]
> **This is not my main forge.**
> My personal and client work lives on **[Framagit](https://framagit.org/caffe-doppio)**.
> I'm here and on [GitLab](https://gitlab.com/caffe-doppio)
and [Codeberg](https://codeberg.org/caffe-doppio) for collaborative projects,
under the same handle everywhere.

<!-- badges: self-hosted SVG, pending the image-rendering audit -->

## How I work

**Governance, security and development tend to be run as three separate worlds**.
They are genuinely different trades, with different skills,
and I am not claiming otherwise. But knowing how each of them thinks
makes you better at your own, and considerably easier to build with.

**I write application code.** What I bring on top of that is
 a habit of reading the whole map before touching any part of it —
 so that when I join an existing project on a narrowly scoped role,
 I find my footing fast, know who to ask which question, and shape
 proposals that already fit the team's security constraints,
 regulatory obligations and actual setup.

**Constraints are inputs, not audits.** Risk analysis
before development. Security considerations from the first draft of the specs.
Data protection questions before the stack is chosen, not after.
None of this is ceremony: it costs an hour early and saves a rewrite later,
and it means everyone sees the same picture whether the team is two people or twelve.

**Shipping faster is not the same as arriving.** Shipping has
never been quicker, and that is not new in kind: copying from
Stack Overflow did the same thing, only slower. What changed
is the delay between a decision and its consequences. What holds at speed
is engineering plus a broad computing and security culture.
I have spent years building both, deliberately.

**Documentation matters.** In short collaborations where everyone
runs their own AI assistants, shared versioned documentation
is what keeps three people and six agents pointed in the same direction.

**Built to be maintained by agents.** Every project I have going is
designed to be maintained through agentic workflows, with me deciding.
That is why the documentation is written for a reader who remembers
nothing of the last session, why the same checks run locally before
a commit and on the forge after it, and why I lean on test-first
development and deterministic tools. A failing test is an instruction
no agent can misread; a linter gives the same answer twice. A model's
judgement varies from one run to the next, so the scaffolding around it must not.

## What I do

<!-- skills cartography: SVG pending, see chantier 6 -->

Backend and tooling in Python. JavaScript at both ends,
Node on the server, plain HTML and CSS when that is what
the job actually needs. TypeScript on Deno when one core has to serve
both a command line and a browser extension. Shell for most of the rest.
TypeScript on Node with Fastify, PostgreSQL and Vue for web apps.
Go for codebase-analysis tooling, where the output has to be the same
twice. Swift for native macOS, picked up in October 2026:
`talk-timer`, my first, is nearly done. Rust, which I am now at ease in,
from a cyber-watch CLI to `beezier`.

I work headless by preference. Appending a line to a file should
take a second, not ten minutes of hunting for the right button,
and when the line does not go at the end, I open it in Vim,
which I came to late and now would not give up. That taste goes
back to BASIC,DOS and Fidonet: I would rather know how a thing works
underneath than know where its interface put the switch.

On the security side, I work the domain-name end of phishing: Unicode
confusables and IDN display policies (UTS #39, IDNA), and passive OSINT
on lookalike domains, from registration data and DNS history to
certificate transparency logs.

Alongside that: data protection and GDPR compliance, risk analysis
with the EBIOS RM framework, threat modelling, and AI governance —
the frameworks and the paperwork, applied with the same
conventions I'd apply to code.

## Selected work

**A GDPR compliance app** <sub>client work, private</sub>
is a data-governance web app for a small business with nobody dedicated
to data protection. A record of processing activities is the base;
data subject requests, breach handling and a threat model are built on it,
since none of them means anything without knowing what is processed.
The app investigates and proposes. Legal basis, retention periods and
breach notification stay a human decision, by design.

Ports and adapters, five ports and nothing else crossing the boundary.
Each layer owns one thing: PostgreSQL the integrity, the domain the
business rules, as pure functions that read the time from a clock port,
route schemas the contract, Vue the display. The browser never recomputes
what the server decided. Specs live in their own repository, and every
test names the requirement or rule it protects.

Around it, a layer of analysis tools in Go. Four of them survey the
codebase: what each file declares, which requirement each test protects,
who writes and reads each table, what each file imports, cites and leaves
to do. Each writes Markdown and JSON from the same survey, committed and
free of line numbers, so a merge request diff shows facts that changed
and nothing else; CI regenerates them and fails on drift. One of them
refuses a table without a declared writer and reader: a personal-data
table nobody reads is processing without a purpose. A fifth, `whatsthis`,
joins the snapshots and answers "what is this?" for a file, a symbol,
a table or a rule ID, rendered in the terminal for me and as JSON for an
agent, from the same facts CI checks. Every snapshot is decoded strictly
against one shared, versioned schema.
> TypeScript on Node (Fastify, Kysely), PostgreSQL, Vue, Go.
> In development since October 2026.

**[`talk-timer`](https://github.com/caffe-doppio/talk-timer)**
plans a talk as blocks inside a total that cannot overflow: lengthening
one block spends the margin, and when the margin is gone, something else
gets shorter. On stage, a floating glass bar above the slides shows
the current block draining away and, near its end, the transition line
to the next one. It never cuts the speaker off.

My first Swift project, built like anything else I ship. The spec comes
first and the code cites its sections; its acceptance criteria run as tests.
The model is a library with no UI framework in it, and every time computation
takes `now` as a parameter. A glossary checked in CI gives each concept one name
per language, English and French. No network, no telemetry, a sandbox with
three entitlements, and a matrix of App Store requirements consulted before any
new API goes in. The development log pairs each new Swift notion with its
Python, Ruby or Rust equivalent.
> Swift, SwiftUI and AppKit, Apache-2.0. In development, for the Mac App Store.

**[`beezier`](https://github.com/caffe-doppio/beezier)**
keeps 2FA recovery codes and recovery keys in one local vault, encrypted
with age, and knows which codes were used, when, and how many are left.
It imports the files services hand out, text or PDF, then removes,
encrypts or keeps the plaintext export, as you choose. The vault is a
standard age file: if beezier disappears, `age -d` still opens it.

Built from a threat model rather than a feature list. The spec maps where
plaintext lives at each step of each user journey. Untrusted exports are
parsed before the vault is unlocked, PDFs in a separate process; every save
is atomic, and a vault written by a newer version is refused rather than
rewritten. Backup keys are plain age recipients: an SSH key, a paper key,
a YubiKey or the Secure Enclave through plugins. The TUI gives every action
a letter, so a phone keyboard over SSH reaches all of them, copies through
OSC 52, and takes its colours from measured contrast on light and dark
terminals. CI runs on three OSes with gitleaks, including a rule that catches
recovery codes themselves, and `cargo audit` weekly. A decision log records
thirty choices, one of them reversed, and why.
> Rust and ratatui, EUPL-1.2. In development.

**`homoeye`**
checks a link for homoglyphs before anyone opens it, without ever contacting
the domain: no DNS query, no request. It flags mixed scripts, invisible and
bidi characters, and whole-script lookalikes. Given a list of protected
brands, it catches `аррӏө.com`, Cyrillic letters with a barred o standing in
for the e, which current Chromium and Firefox display as plain Unicode,
with no warning.
`--explain` shows why, character by character: code point, Unicode name,
script, and which reading turned it into the brand.

It started in Python and moved to TypeScript on Deno once a browser extension
had to share its core. The core is runtime-free. The Unicode 18 tables are
generated from the UCD, each source pinned by its sha256, and Chromium's own
lookalike rules come in at a pinned commit. A 60-case corpus is the oracle,
its expected UTS #39 skeletons computed by an independent script. Every rule
was mutation-tested, and a first measurement on 1,480 real IDNs from the
Tranco list raised no alert from the brand-free rules. The compiled binary
holds no permission and cannot reach the network. And since an AI assistant's
editing tool once slipped a raw right-to-left override into the tests, a test
now runs homoeye's own tables over the whole repository.
> TypeScript on Deno, EUPL-1.2. Pre-alpha; the repository opens with
> the first release.

**[`gitkeep`](https://framagit.org/caffe-doppio/gitkeep-pipx)**
walks a tree bottom-up and drops a `.gitkeep` into every empty directory,
so Git actually tracks the scaffolding you designed. It reads
the root `.gitignore`, runs dry by default, and deliberately
refuses to delete placeholders again: removing files on a tree
someone merely pointed at needs a better safety story than one flag.
> Python, AGPL-3.0.

More on [Framagit](https://framagit.org/caffe-doppio).
Mirroring a selection here is on the list, below.

## Currently

- [ ] Taking `homoeye` to a first public release: CI, signed binaries,
      then a Firefox extension on the same core, for organisations to
      deploy with their own list of protected brands.
- [ ] Taking `talk-timer` to the Mac App Store, free. The planner works;
      wiring Start to the floating bar is next.
- [ ] A web companion to `dechetri-cli`, my waste-collection scheduler. The
      hard part is already done: the local open-data API is genuinely painful,
      and it now yields usable `.ics` calendars. The web version exists to plug
      other open-data sources into the same wrapper.
- [ ] A cyber-watch CLI for the **[RadioCSIRT](https://www.radiocsirt.org)**
      podcast, extracting IOCs and sources for CTI analysts. My first Rust
      project. I am taking my time on purpose.
- [ ] Headless CLI wrappers for Grist. Deliberately against the grain — pulling
      a no-code cloud tool down to a local terminal — so that people who need
      calendar exports, mail templates or task automation get them without
      hand-writing API calls.
- [ ] Mirroring two or three of the above here.

<sub>Last reviewed: October 2026. If these boxes have not moved
in a while, that is information too.</sub>

## Contact

[sasha@etdeuxmains.fr](mailto:sasha@etdeuxmains.fr), signed mail welcome.

```text
4556 8EAB 0E8A B7B0 0B3B  2F5F AF8B 937D 934C 5119
```

Everything I commit is signed with that key. The rest of the links are in the sidebar.

<details>
<summary>Two things that explain more than a skills list</summary>

<br>

💬 My first programming language was BASIC, on
a **UKNC MS 0511** — a Soviet PDP-11 clone. Starting on hardware
that was a copy of something else, with documentation that assumed
you would work it out, turned out to be decent training for the rest of it.

☕️ The handle is about coffee, of which I drink a great deal.
It is also about compression. I keep scripts that scaffold
entire directory trees with placeholders, so an alias and two arguments
produce in seconds what would otherwise be twenty clicks.
Same idea as the drink: one thing done properly, in a smaller cup,
rather than two things at once.

</details>

## On AI assistance

> [!IMPORTANT]
> I use AI assistance in my work, including on some of the code linked here.
> It contributes to drafting, review and refactoring.
> I make the decisions, I read what I ship, and I remain responsible
> for it including the parts I did not type myself.
>
> I work to the **4D framework** for AI fluency —
> Delegation, Description, Discernment, Diligence —
> from Anthropic Academy's *AI Fluency: Framework and Foundations*,
by Rick Dakan and Joseph Feller. Diligence is the part that
matters here: disclosing the use, verifying the output, owning the result.
>
> AI compliance and governance are part of what I work on
professionally, so saying this out loud is the minimum I owe my own position.

<!-- doppio(doppio(x)) != doppio(x)
     Not idempotent. Neither is asking the same question twice. -->
