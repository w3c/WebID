
# Working with the WebID specification toolchain

The WebID CG writes their W3C documents using [Bikeshed](https://speced.github.io/bikeshed/), a preprocessor that automates a lot of modern spec-writing and allows one to write most of a specification's content in Markdown. This guide provides a short introduction to its main features. For more information, please see the full [Bikeshed specification](https://speced.github.io/bikeshed/).


## Setup and usage

The source files of the WebID specifications are Bikeshed files, ending in the `.bs` extension. Each document has a main source file called `index.bs`; to generate the corresponding `index.html` specification file, we run the Bikeshed processor on that source file. There are multiple ways you can use the Bikeshed processor.

  - With [pipx](https://pipx.pypa.io/) (with Python `>3.9`):
  
    - either install Bikeshed locally (`pipx install bikeshed`) and run `bikeshed index.bs`,
  
    - or run it on the fly with `pipx run bikeshed index.html`.
  
  - Using the Bikeshed API:

    ```curl https://api.csswg.org/bikeshed/ -F file=@index.bs > index.html```

  - Via the [Web Form](https://api.csswg.org/bikeshed/): either upload `index.bs` or point the form to a URL that provides it.


## The anatomy of a Bikeshed file

A Bikeshed source file is written in HTML, but also allows most features of the popular [CommonMark](https://commonmark.org/) dialect of Markdown ([spec](https://spec.commonmark.org/current/), [cheatsheet](https://commonmark.org/help/)), which the preprocessor transforms to HTML for you.


### Boilerplate

Bikeshed relieves you off writing a lot of boilerplate, and instead generates the relevant HTML portions based on metadata and templates. This includes a table of contents, a header with all relevant metadata, an abstract, a status text, a section on conformance, a bibliography of references and several indexes.

Boilerplate generation can be fully customized, as described in the [relevant section of the Bikeshed specification](https://speced.github.io/bikeshed/#boilerplate), but for most purposes, the default templates are sufficient.


### Metadata

Metadata about the specification, as well as configuration for the preprocessor, is passed to Bikeshed in `<pre class='metadata'>` blocks. A number of metadata fields are required, and are listed in the following example. There details, as well as other possible fields, can be found in the [relevant section of the Bikeshed specification](https://speced.github.io/bikeshed/#metadata).

```html
<pre class='metadata'>
Title: Web Identity and Discovery 1.0
Shortname: WebID 1.0

Group: w3c
Status: w3c/ED
Level: none

Editor: Jacopo Scazzosi, jacopo@scazzosi.com

URL: https://www.w3.org/2005/Incubator/webid/spec/identity/

Abstract: 

  A global distributed Social Web requires that each person be able to control their identity [...]
</pre>
```

Most metadata about the specification is included in the specification's header. Should some important piece of metadata be missing, custom fields can easily be included by prefixing their name with an exclamation mark, e.g., `!Keywords: webid, identity, rdf`.


### Definitions

A crucial part of a specification is the definition of its terminology. Definitions can easily be indicated by surrounding the term with `<dnf>` tags; Bikeshed will automatically add a fragment identifier. Alternatively, Bikeshed provides a shorthand for definition lists:

```html
: Foo
:: To Foo means to do something with a Bar.

: Bar
:: A Bar is something that is used when Fooing. 
```


#### Autolinks

Bikeshed facilitates referencing to both internal and external terminology throughout the text of a specification, by automatically linking terms wrapped as `[=Foo=]`. It recognizes most plurals, conjugations etc.; alternative terms that trigger autolinking (e.g., synonyms, abbreviations) can be added with the `lt` attribute, e.g., `<dfn lt='ACME|AcmeCorp'>Acme</dfn>`. For example, given the above definitions, you can write:

```html
This document defines [=AcmeCorp=], and what it means to be [=Fooing=] with [=Bars=].
```

Autolinks will also be created for terms exported by any of the specifications in the [SpecRef](https://specref.org) database (including W3C and IETF documents). To make sure Bikeshed links to the correct definition, in case multiple documents define the same term differently, preferences can be configured in a `<pre class='link-defaults'>` block, or in a file called `link-defaults.infotree`, according to the [InfoTree](https://speced.github.io/bikeshed/#infotree) syntax. For example:

```
info: link-defaults
  type: dfn;
    text: Client; spec: SOLID
    text: Server; spec: SOLID
```

Using the same syntax in an `<pre class='anchors'>` block, or in a file called `anchors.bsdata`, you can also add terms for documents that do not export them, or are not in SpecRef. For example: 

```
spec: FOAF; urlPrefix: http://xmlns.com/foaf/0.1/#term_; 
  type: dfn;
    text: foaf:Agent; url: Agent
    text: foaf:Person; url: Person
    text: foaf:Organization; url: Organization
```

For a number of well-known specifications and definitions, Bikeshed provides a special notation and styling. This includes HTTP headers (e.g., `[:Content-Type:]`), HTML tags (e.g., `<{div}>`) and CSS properties (e.g., `'border'`). More can be found in the [relevant section of the Bikeshed specification](https://speced.github.io/bikeshed/#autolink-microsyntax). 


### References

Bibliographic references can be included as simple as `[[HTTP]]`, for informative references, and `[[!OIDC]]`, for normative rerences. An alternative textual appearance can be indicated as `[[WEBID|The WebID specification]]`. Other modifiers can be found in the [relevant section of the Bikeshed specification](https://speced.github.io/bikeshed/#biblio).

All documents in the SpecRef database have keys that will automatically be recognized (mostly their abbreviation or RFC identifier). Other documents can be added in a `<pre class="biblio">`, or in a `biblio.json` file, formatted according SpecRef's [entry syntax](https://github.com/tobie/specref). For example:

```json
{
  "SOLID": {
    "href": "https://solidproject.org/TR/protocol",
    "title": "Solid Protocol",
    "date": "2020",
    "authors": [
      "Sarven Capadisli",
      "Tim Berners-Lee",
      "Ruben Verborgh",
      "Kjetil Kjernsmo"
    ]
  }
}
```


### Other Bikeshed features

Bikeshed is very configurable and provides a lot of extra features. For a comprhensive overview, see the [Bikeshed specification](https://speced.github.io/bikeshed/). This last section highlights a few interesting ones.


#### Section identifiers

Bikeshed supports the [Markdown Extra](https://michelf.ca/projects/php-markdown/extra) notation for adding fragment identifiers to sections by adding `{#id}` after it. Refering to a section can then be done similar to other references, as `[[#id]]`. Bikeshed then automatically formats the reference as a link with a section sign. For example:

```md
# This is an example section #  {#sec-example}

For some reason [[#sec-example]] refers to itself.
```

This also works to refer to sections of other documents, by combining both reference notations: `[[WEBID#introduction]]`.


#### Text Macros

Out of the box, Bikeshed provides a number of macro's that allow for easy reuse of most metadata. They can be used in the text as `[MACRO]`, e.g., `[DATE]`

Additional macro's can be configured in a `<pre class="metadata">` block. For example:

```html
<pre class="metadata">

Text Macro: W3C <abbr title="World Wide Web Consortium">W3C</abbr>
Text Macro: NO-NORM *This section is non-normative.*
Text Macro: MUST <em class="rfc2119">MUST</em>

</pre>

Specifications of the [W3C] include normative and informative (non-normative) sections. The former can contain conformance terms like [MUST]. The latter can be indicated with a short line stating "[NO-NORM]".
```

For more info, see the [relevant section of the Bikeshed specification](https://speced.github.io/bikeshed/#text-macros).


#### Asides: notes, issues, examples ...

Bikesheds supports multiple blocks aside the main text, which are formatted according to their nature. They can be indicated either by adding a class to a block, e.g., `<div class="example"></div>`, or by beginning a paragraph with their name, followed by a colon: `Note: ...`.

Issues can also refer to a remote issue tracker, by setting the `Repository` metadata field and starting the paragraph with the issue number, e.g., `Issue(123): ...`.


#### Code blocks

Text in `<code></code>` elements and `<pre></pre>` blocks are automatically formatted as code. In the latter case, Bikeshed also strips the minimal indent from all lines, to avoid an awkward layout when reading the source file.

Syntax highlighting is supported for most [Pygment lexers](http://pygments.org/docs/lexers/), using the `highlight` attribute, and line numbers can be added using the `line-numbers` attribute or with the `Line Numbers` metadata field. Moreover, specific lines of a code block can be highlighted using the `line-highlight` attribute. Here's an example:

```html
<div class='example'>
  A code block in an example:

  <pre highlight="js" line-numbers line-highlight="1,3">
    const x = "Hello World!";
    // less interesting comment ...
    console.log(x);
  </pre>
</div>
```

Code snippets can also be imported from other files as follows:

```html
<pre class=include-code>
path: hello-world.js
highlight: js
line-numbers:
line-highlight: 1,3
</pre>
```


#### Validation checks

A number of typical pitfalls that specifications can bump into can be checked by the Bikeshed processor on transpilation. These include checks for broken links, and whether conformance language is used in non-normative sections. They are enabled with the `Complain About` metadata field.
