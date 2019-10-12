# Branches
This project makes heavy use of Git branches. The `master` branch contains the
current, pristine documentation state. `master` must not contain partial
documents. See the [stages](stages.md) document for more information about
partial documents.

A partial document is to be held within its own branch; one branch per document.
For such a branch on this repository, it's name should be the name of the
primary entity being documented. If an ambiguity arises, include names of the
directories ancestral to the document until it is no longer ambiguous. For
example:

- Ongoing work of the "Platform" class is held in the `Platform` branch.
- Meanwhile, if work begins on the "Platform" enum, that work is held in the
  `enum/Platform` branch.
- Though not required, the original `Platform` branch may be renamed to
  `class/Platform` to improve clarity.

The special `partial` branch is an empty branch that writers may submit pull
requests against to indicate that they wish to create a new branch containing
partial content.

This naming scheme applies to branches in the project repository. Branch names
within forks or pull requests are local to that repository, and so do not have
to follow this scheme.
