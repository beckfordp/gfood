# gfood

A food-delivery application: customers order, restaurants cook, couriers deliver. The
first application built on the Gluon platform as its own repo; gshop, the exemplar the
platform grew with, stays inside gluon.

Status: discovery. The domain, personas and story map are agreed; how gfood uses gluon,
its services and its frontends come next.

## Start here
- [Primer](./docs/primer.md): the domain in one sitting
  ([as a page](./docs/diagrams/primer.html)).
- [Personas](./docs/personas.md): the five people gfood serves.
- [Story map](./docs/story-map.md): the backbone and the release slices (R0–R3).
- [User stories](./docs/user-stories.md): the walking skeleton (R0) as stories.
- [Open questions](./docs/open-questions.md): what isn't decided yet.
- [ADRs](./docs/adr/): gfood's own decisions (none yet).

## gluon as the substrate
gfood builds on what gluon already has rather than starting again:

- **Services:** gluon's Rust services (`services/*-rs`: user, payment, notification,
  order, catalog, cart, inventory, fulfilment).
- **Tools:** `tools/rust-service-template` for new services; `tools/gluon-kube` to run
  them in the sandbox.
- **Libraries:** `lib/gluon-rs` (HTTP, persistence, events, telemetry, testing).
- **Ways of working:** Conductor and its `workflow.md`, gluon's user-story format, ADRs,
  the contract harness (`tests/contract`) and the Playwright acceptance suite
  (`tests/acceptance`), the sandbox's export and save.

## Reuse is harvested
1. **As is** where a gluon service fits: gfood runs its own instance of it.
2. **Copied** where it needs changes: gfood copies the service into `services/` with a
   `gf-` prefix (`gf-order-service-rs`) and changes its own copy.
3. **Folded back** where a change is generic: gfood raises a change request in that
   service's gluon backlog (`services/<service>-rs/conductor/tracks.md`, `## Backlog`,
   "CR from gfood: …"), to be taken into the gluon service later.

Using as is and copying pull against each other: a copy is quick and free to change but
drifts from gluon; as is keeps one service but constrains gfood. Where the line falls is
open, to be settled here.

## Layout
```
gfood/
├── conductor/      product, tech stack, workflow, tracks
├── docs/           primer, personas, story map, user stories, open questions, ADRs
├── services/       gfood's services, own and gf- copies, each its own repo (gitignored here)
└── frontends/      gfood's frontends, each its own repo (gitignored here)
```

gfood lives in gluon's checkout at `apps/gfood`, its own repo, gitignored by gluon.

## License
MIT, as gluon: [LICENSE](./LICENSE). Every file in gfood and its service and frontend
repos that takes a comment starts with `SPDX-License-Identifier: MIT` in that comment,
after any shebang or doctype: Rust, TOML, YAML, Dockerfiles, shell, Python, SQL,
TypeScript, HTML (`// …`, `# …`, `-- …`, `<!-- … -->`). Markdown, JSON, lockfiles,
`.gitignore` and `LICENSE` don't take one. Nor do copied third-party files (they keep
their own licence, named in a NOTICE beside them) or generated and captured output. Each
repo carries its own `LICENSE`.

## In the sandbox
gluon's sandbox export carries gfood (`bin/lib/sandbox.py`, `SHARED_REPOS` and
`SANDBOX_REPOS`); from gluon on the laptop:

```sh
bin/sandbox-export --app gfood     # gfood-gluon.tar.gz: no Scala, no plans
```

`bin/sandbox-save` in the sandbox brings gfood's commits back.
