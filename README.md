# gfood

A food-delivery application on the Gluon platform: customers order, restaurants cook,
couriers deliver. The second application on gluon after gshop, and the first built as
its own repo ([gluon ADR 0031](../../docs/adr/0031-multi-app-platform.md)).

Status: discovery. The domain, personas and story map are agreed; services and a
frontend come next, built in the sandbox.

## Start here
- [Primer](./docs/primer.md): the domain in one sitting.
- [Personas](./docs/personas.md): the five people gfood serves.
- [Story map](./docs/story-map.md): the backbone and the release slices (R0–R3).
- [User stories](./docs/user-stories.md): the walking skeleton (R0) as stories.
- [Open questions](./docs/open-questions.md): what isn't decided yet.
- [ADRs](./docs/adr/): gfood's own decisions.
- [`app.yaml`](./app.yaml): the platform services gfood uses and its own services.

## Layout
```
gfood/
├── app.yaml        platform services used + gfood's own services
├── conductor/      product, tech stack, workflow, tracks
├── docs/           primer, personas, story map, user stories, ADRs
├── services/       gfood's own services, each its own repo (gitignored here; none yet)
└── frontends/      gfood's frontends, each its own repo (gitignored here; none yet)
```

gfood lives in gluon's checkout at `apps/gfood` (gitignored by gluon). Platform
services stay in gluon's `services/` and are never copied here. Deployment values
(`environments/local/`) arrive with the first deployable service.

## In the sandbox
gluon's sandbox export carries gfood (`bin/lib/sandbox.py`, `SHARED_REPOS` and
`SANDBOX_REPOS`); from gluon on the laptop:

```sh
bin/sandbox-export --no-plans --prefix gfood     # gfood-gluon.tar.gz
```

`bin/sandbox-save` in the sandbox brings gfood's commits back.
