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

These are skills for Claude, not a command-line tool. There is nothing to
install and nothing to import — you describe the work and the matching skill
fires on its own.

**In Claude Code or Cowork**, once the skills are on your machine:

```bash
bash ~/Desktop/agent/_setup/sync-skills.sh
```

That clones every agent repository and links its `skills/` into `~/.claude/skills`,
so they are available in every session and every folder. Re-run it whenever the
daily loop ships something new — it pulls rather than re-clones.

Then simply ask. Each skill's `description` frontmatter is written to match how
the request actually gets phrased, in English or Turkish, so you do not name the
skill and generally should not have to think about which one applies.

**If nothing fires**, that is a defect in the skill rather than in how you
asked. The description was written for the wrong phrasing. Say what you asked
and what you expected, and it gets fixed — that feedback is more valuable than
working around it.

**What is actually built** is the Done section of [BACKLOG.md](BACKLOG.md).
Everything under Queue is planned and does not exist yet. The daily loop builds
one item a day; the table above is the intended shape, not the current state.

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

## Roadmap

See [BACKLOG.md](BACKLOG.md). The first unchecked item is the one being built.

## Planned contents

Nothing here is built yet. This table is the intended shape, and the daily loop
fills it in one item at a time.

| # | Skill | What it does |
| --- | --- | --- |
| 001 | [storyline-first](skills/storyline-first) | Settle the argument as a sequence of sentences before any slide exists. |
| 002 | [action-titles](skills/action-titles) | Write every headline as the point the slide makes rather than the topic it covers. |
| 003 | [one-slide-one-job](skills/one-slide-one-job) | The test each slide has to pass, and what to do with a slide that fails it. |
| 004 | [evidence-per-claim](skills/evidence-per-claim) | Attach the source and vintage to every number on a slide, kept where the deck can be checked later rather than in someone's memory. |
| 005 | [chart-choice](skills/chart-choice) | Choose the chart form from the comparison the reader has to make, with the standard mistakes named. |
| 006 | [executive-summary-page](skills/executive-summary-page) | Write the page that has to work alone, because it is the only one some readers will see. |
| 007 | [appendix-discipline](skills/appendix-discipline) | What belongs behind the appendix divider and why moving something there is usually the right call. |
| 008 | [build-the-file](skills/build-the-file) | Produce the file from the settled storyline, with the structure carried through rather than reconstructed. |
| 009 | [dry-run-questions](skills/dry-run-questions) | Generate the questions the audience will actually ask, ranked by how badly each one would land, and where in the deck each answer should already be. |

## Licence

MIT. See [LICENSE](LICENSE).
