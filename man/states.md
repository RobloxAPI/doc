# States
A document describes a primary entity, as well as a number of secondary
entities. Each entity within a document has one of the following **states** of
completeness:

- `absent`: The entity has no presence within the document. The primary entity
  never has this state.
- `dirty`: The entity has a description, but the content is incomplete or
  unverified according to the document's current [stage](stages.md).
- `pristine`: The description of the entity is complete and verified according
  to the document's current stage.

Each document also has its own state:

- `missing`: There exists a primary entity, but the corresponding document file
  is not present.
- `draft`: The document file exists, but contains one or more `dirty` entities.
- `spotless`: The document contains no `dirty` entities.
- `perfect`: The document only contains `pristine` entities.

Note that `draft` and `spotless` documents may contain `absent` entities. That
is, a document does not need to contain every entity in order to be considered
`draft` or `spotless`.

States are assigned in relation to the API. As long as a document has a
corresponding entity, it "exists" even if it is not present in the repository.
This is the meaning of the `missing` state.

Because of periodic modifications to the API, document states can switch
passively, even if the content of the document does not change. For example,
when an primary entity receives an additional secondary entity (i.e. updated
API), the `perfect` document corresponding to that entity will passively
downgrade to `spotless`. This is due to the additional secondary entity having a
state of `absent`.

Branches in the project repository may only contain documents of certain states.
See the [branches](branches.md) page for more information.
