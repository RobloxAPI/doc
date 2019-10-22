# File structure
This page describes how the project repository is structured.

All documents and related files are located under the `src/` directory.

<dl>

<dt><code>src/</code></dt>
<dd>

The root of the document file tree.

</dd>

<dt><code>src/res/</code></dt>
<dd>

Global resources; embedded images, video, audio, attachments, etc. May contain
subdirectories. Files are visible to all documents.

</dd>

<dt><code>src/doc/</code></dt>
<dd>

Root location of documents.
</dd>

<dt><code>src/doc/$LANG/</code></dt>
<dd>

Documents of a specific language. `$LANG` is an IETF language tag, indicating
the language of the contained documents. For example, `en` represents English.
This directory only contains directories.

</dd>

<dt><code>src/doc/$LANG/$CATEGORY/</code></dt>
<dd>

Documents of a particular category.

Any descendant document of the form `$NAME.md` may have an optional sibling
directory called `$NAME` which contains resource files visible only to that
specific document.

</dd>

<dt><code>src/doc/$LANG/api/</code></dt>
<dd>

Documents of the API category. These are structured to fit with generated API
pages.

</dd>

<dt><code>src/doc/$LANG/api/$TYPE/</code></dt>
<dd>

API entities namespaced by type. These correspond to the `class`, `enum` and
`type` entity types.

</dd>

<dt><code>src/doc/$LANG/api/$TYPE/$PRIMARY.md</code></dt>
<dd>

The combination of `$TYPE/$PRIMARY.md` indicates a file that documents the
referred API entity. For example, `class/Workspace.md` documents the *Workspace*
*class*.

</dd>

</dl>

Here are some examples:

- `src/doc/en/api/class/Workspace.md`: Document for the Workspace class in English.
- `src/doc/es/api/enum/NormalId.md`: Document for the NormalId enum in Spanish.
- `src/doc/de/api/type/Vector3.md`: Document for the Vector3 type in German.
- `src/doc/de/api/type/Vector3/example.png`: Resource visible only to `Vector3.md`.

### File types
Documents have the `.md` file extension, indicating a Markdown file.

Resource file types include anything that can be referred by or embedded into an
HTML file.
