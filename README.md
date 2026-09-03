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

## What I do

<!-- skills cartography: SVG pending, see chantier 6 -->

Backend and tooling in Python. JavaScript at both ends,
Node on the server, plain HTML and CSS when that is what
the job actually needs. Shell for most of the rest. Currently
learning Rust, and starting C.

I work headless by preference. Appending a line to a file should
take a second, not ten minutes of hunting for the right button,
and when the line does not go at the end, I open it in Vim,
which I came to late and now would not give up. That taste goes
back to BASIC,DOS and Fidonet: I would rather know how a thing works
underneath than know where its interface put the switch.

Alongside that: data protection and GDPR compliance, risk analysis
with the EBIOS RM framework, threat modelling, and AI governance —
the frameworks and the paperwork, applied with the same
conventions I'd apply to code.

## Selected work

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

<sub>Last reviewed: September 2026. If these boxes have not moved
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
