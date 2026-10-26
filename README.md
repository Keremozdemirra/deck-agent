# deck-agent

Agents and skills for presentations, where the argument is decided before the first slide.

Most decks are written slide by slide and it shows: the argument
appears somewhere in the middle, the same point is made three times in different
words, and the recommendation is a bullet on slide 34 rather than the thing
everything else was building towards.

This repository holds the agents and skills for the other order. The storyline
is settled first, as sentences. Each slide then has one job, and a slide that
cannot state its job in a sentence does not get built.

## What this is not

It is not a template pack and does not supply a house style. Where a
file has to be produced, the skills call a generator.

It is not a design tool. Making a slide beautiful is worth doing after it is
worth showing.

It does not do the underlying analysis.

## How to use this

These are skills for Claude. There is nothing to
build and nothing to import: you describe the work and the matching skill
fires on its own.

**In Claude Code**, clone the repository and link its skills into the
folders Claude Code reads (`~/.claude/skills/`):

```bash
git clone https://github.com/Keremozdemirra/deck-agent ~/agent-packs/deck-agent
cd ~/agent-packs/deck-agent
mkdir -p ~/.claude/skills
for s in skills/*; do ln -sfn "$PWD/$s" ~/.claude/skills/; done
```

The links point back into the clone, so `git pull` there brings in whatever
ships next. To copy the files instead of linking them, replace the
line starting with `for` with:

```bash
cp -R skills/* ~/.claude/skills/
```

Skills placed there are available in every session and every folder; start a
new session after installing.

Then simply ask. Each skill's `description` frontmatter is written to match how
the request actually gets phrased, in English or Turkish, so you do not name the
skill and generally should not have to think about which one applies.

**If nothing fires**, that is a defect in the skill rather than in how you
asked. The description was written for the wrong phrasing. Say what you asked
and what you expected, and it gets fixed. That feedback is more valuable than
working around it.

**What is actually built** is listed under Contents below and in the Done
section of [BACKLOG.md](BACKLOG.md). Everything under Queue is planned and does
not exist yet.

## Layout

```
agents/
  <name>.md           one specialist, its brief and its boundaries
skills/
  <name>/
    SKILL.md          the instruction, with triggering description frontmatter
    scripts/          only where deterministic code beats instruction
examples/
  <name>/             worked example on real input, with the output committed
```

`agents/` is empty so far.

## Roadmap

See [BACKLOG.md](BACKLOG.md). The first unchecked item is the one being built.

## Contents

| Skill | What it does |
| --- | --- |
| [storyline-first](skills/storyline-first) | Settle the argument as a sequence of sentences before any slide exists. |

Everything still under Queue in [BACKLOG.md](BACKLOG.md) does not exist
yet.
## Licence

MIT. See [LICENSE](LICENSE).
