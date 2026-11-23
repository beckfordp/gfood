# Product Guidelines — gfood

## Language
Use the domain's words ([primer glossary](../docs/primer.md#words-the-domain-uses)):
basket, menu, sold out, prep time, offer, dispatch, proof of delivery. The same word in
stories, APIs, events and UI.

## Stories
- The [story map](../docs/story-map.md) is the source; a story that changes the map
  changes the map first.
- Stories are written per release slice, in gluon's `docs/user-stories.md` format
  (US-N, tasks naming the service).

## Platform boundary
- Platform services (gluon `services/`) are used as they are. A needed change goes to
  that service's own backlog, never into a copy or a gfood-specific code path in it.
- gfood's own services hold gfood's nouns (restaurant, courier, offer).
- Decisions that change a platform service are gluon ADRs; gfood-only decisions are
  ADRs here.

## Repo hygiene
- Commits: `<type>(<scope>): <description>`, one line.
- Never commit `.idea/` or `.claude/`.
