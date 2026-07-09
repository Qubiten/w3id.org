# /qubiten/

Permanent identifiers for Qubiten. The `qubiten/` space allocates **one sub-prefix per source of
record**; each sub-prefix is administered by its own registration authority and resolves by the mode
its records require. The allocation is registered here and enforced by `./.htaccess`.

## Namespace-allocation table

| Sub-prefix | Source of record (repo) | Registration authority | Interim target | Resolution mode | Status |
|---|---|---|---|---|---|
| [`mr/`](https://w3id.org/qubiten/mr/) | [metadata-registry](https://github.com/Qubiten/metadata-registry) — ISO/IEC 11179 registry | Wilbye (Qubiten) `wilbye@qubiten.com` | repository documentation | **302** to docs (opaque redirect) | Active |
| [`meta-architecture/`](https://w3id.org/qubiten/meta-architecture/) | [meta-architecture](https://github.com/Qubiten/meta-architecture) — architecture-governance corpus | Wilbye (Qubiten) `wilbye@qubiten.com` | committed corpus/spine serialisations (raw GitHub) | **303** content negotiation (httpRange-14) | Active |

Unique sub-prefix is registered **before** any IRI under it resolves — no IRI is minted against an
unallocated prefix.

## `mr/` — resolution detail

* [`https://w3id.org/qubiten/mr/`](https://w3id.org/qubiten/mr/) — namespace root; redirects to the
  registry's documentation index.
* [`https://w3id.org/qubiten/mr/ra/qubiten`](https://w3id.org/qubiten/mr/ra/qubiten) — the
  registration authority identifier.
* All other IRIs under `https://w3id.org/qubiten/mr/` redirect (interim, **302**) to the source
  repository, <https://github.com/Qubiten/metadata-registry>, until the registry's HTTP containers
  are publicly deployed.

## `meta-architecture/` — resolution detail

Opaque, persistent PIDs answered by **303 See Other** content negotiation (W3C *Cool URIs*; *Best
Practice Recipes for Publishing RDF Vocabularies*). The IRI carries the opaque id, never the label.

* `.../meta-architecture/id/<opaque>` — a corpus administered record. `text/turtle` →
  `docs/registry/corpus.ttl`; `application/(ld+)json` → `corpus.json`; otherwise the GitHub blob.
* `.../meta-architecture/spine/<opaque>` — a production-spine / domain node. `text/turtle` →
  `production/out/spine.ttl`; `application/(ld+)json` → `spine.json`; otherwise the reading index.
* `.../meta-architecture/ns` (with `#<term>`) — the `marec:` vocabulary hash namespace
  (`https://w3id.org/qubiten/meta-architecture/ns#`). Served, per the *swbp-vocab-pub* hash-namespace
  recipe, as a single document from the corpus graph in which its terms are exercised. **Interim:** a
  dedicated ontology serialisation is a flagged follow-up — until it is minted, the namespace resolves
  to the corpus graph.
* `.../meta-architecture/` — namespace root; redirects (**302**) to the corpus reading index.

All `meta-architecture/` targets are **interim**: the committed serialisations on raw GitHub, to be
superseded when the platform serves dereferenceable resources directly.

## Contact

This space is administered by:

**Wilbye (Qubiten)**

Email: [wilbye@qubiten.com](mailto:wilbye@qubiten.com)
GitHub: [Qubiten](https://github.com/Qubiten)
