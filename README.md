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
