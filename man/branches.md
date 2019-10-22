# Branches
This project makes heavy use of Git **branches**. Branches in the project
repository may only contain documents of certain states:

Branch    | Allowed states
----------|---------------
`master`  | `perfect`, `spotless`, `missing`
(draft)   | `perfect`, `spotless`, `draft`, `missing`
(fork/PR) | `perfect`, `spotless`, `draft`, `missing`

See the [states](states.md) page for more information about states.

The `master` branch contains current, unblemished documentation. That is, it may
only contain `perfect`, `spotless`, and `missing` documents, and cannot contain
`draft` documents.

A `draft` document can exist in the repository, but must be held within its own
"draft" branch. One branch per document, one document per branch. The name of
such a branch must be the file path to the document, minus the file extension.
Non-English documents must include the language directory.

For example, a draft of the `Instance.md` document, describing the Instance
class, would live in the `api/class/Instance` branch. The Spanish version would
live in the `es/api/class/Instance` branch.

This naming scheme applies to draft branches in the project repository. Branches
within forks or pull requests are local to that repository, and so do not have
to follow this scheme.

Draft branches are ephemeral. Once the document is reviewed and promoted to
`spotless` or `perfect`, the commits are rebased and merged into `master`, and
the draft branch is deleted.

The literal `draft` branch is an special empty branch that writers may submit
pull requests against to indicate that they wish to create a new branch
containing drafted content. Such pull requests are later redirected to the
correct branch by a member of the project.
