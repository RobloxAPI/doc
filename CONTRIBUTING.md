# Contributing
This page provides information on contributing to the Roblox API Reference
Documentation project.

#### Ownership
It's great if you've spent significant time and effort on a document, but this
doesn't mean you "own" it. Documents belong to all contributors of the project,
so expect content you've written to be revised without mercy. Take pride in the
contribution, not the content.

## Submitting issues
Issues usually fall into one of a number of types:

- **enhancement**: Something could be improved. Feature requests.
- **error**: Something is incorrect. Usually involves taking a direct action to
  solve the problem.
- **question**: Something is unclear. Usually results in a clarification of the
  subject.

Issues also usually have a broad subject:
- **content**: Regarding the actual content of an API document.
- **syntax**: Regarding spelling, grammar, and so on. Separate from content,
  because these are usually minor.
- **meta**: Regarding the project itself. This can involve the manual,
  formatting that affects all API documents, and so on.

Though not required, the submitter will benefit by focusing their issue on a
type and subject as described above.

Other statuses that may appear:
- **duplicate**: The same issue was already submitted previously.
- **needs info**: Not currently actionable; more information is needed from the
  submitter.
- **invalid**: Closed due to being irrelevant to the project or otherwise
  unsuitable.
- **aged**: Closed due to long period of inaction. Can be reopened if an action
  is taken since.
- **grouped**: Closed due to containing multiple issues within a single
  submission. Each issue should be resubmitted individually.

When submitting an issue regarding a specific document, the path to the document
should be included in the title. For example:

> ### [api/class/Instance] Incorrect description of ChildAdded

## Creating pull requests
The submitter may also make pull requests to directly address an issue
themselves.

### Submitting documents
When submitting a pull request regarding a specific document, the path to the
document should be included in the title. For example:

> ### [api/class/Instance] Add example for ChildAdded

A writer may submit a complete document by creating a pull request against the
`master` branch. This pull request will be reviewed by a member of the project,
who will check the content for accuracy, wording, and completeness. The reviewer
may suggest improvements, or make edits against the pull request directly. The
submitter should work with the reviewer to make the content pristine. The
document will be merged once it meets standards. See the [stages](man/stages.md)
page for more information on requirements.

A writer may also submit partial documents, or drafts. Drafts live in branches
in the repository. If a branch for a draft exists, then the writer may submit a
pull request against that branch directly. It will be compared against the
content that already exists in that branch.

GitHub does not allow pull requests to be made against branches that do not
exist. For this reason, the `draft` branch exists. Pull requests made against
this branch indicate to reviewers that the submitted document is incomplete, and
the repository does not yet have a branch for that document. After the document
is reviewed and refined, the reviewer will create a new branch and redirect the
pull request to it.

Attempting to submit multiple documents within a single pull request is invalid.
Such pull requests will be closed, and the writer should resubmit each document
individually.

See the [branches](man/branches.md) page for more information about branches in
this repository.
