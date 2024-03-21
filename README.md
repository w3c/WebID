
# WebID Community Group

This repository contains the source code of the [W3C WebID Community
Group](https://www.w3.org/groups/cg/webid/) (CG) processes and work items.

## Participation

All substantive contributors to work items must be members of the WebID CG.
It’s easy to [join the CG](https://www.w3.org/community/webid/join) if you’d
like to contribute. Guests are welcome but do not have voting rights.

## Contributing

See the [contributing
guide](https://github.com/w3c/WebID/blob/main/CONTRIBUTING.md) for detailed
instructions on how to get started with our project.

Work items are written using either [BikeShed][bikeshed] or [ReSpec][respec].

> [ReSpec][respec] is a JS library that unobtrusively allows editors to write a 
> specification focusing on the actual features and correctness, while needing
> to pay as little attention as possible to issues pertaining to styling,
> referential integrity and W3C Publication Rules. 

> [BikeShed][bikeshed] is a preprocessor that automates a lot of modern
> spec-writing, taking in lightly-decorated Markdown and producing a full spec,
> with cross-spec autolinking, automatic generation of indexes/ToC and many
> other features. 

Moving forward, all new work items and major revisions of existing work items
should use [BikeShed][bikeshed]. [BUILD.md][BUILD.md] contains a short guide on
its usage.

An [automated CI workflow using GitHub Actions][workflow] takes care of
maintaining up-to-date builds of work items written with [BikeShed][bikeshed].
The resulting `.html` documents are tracked in separate branches with the `ci/`
prefix prepended to the name of the originating branch.

## Code of Conduct

All documentation, code and communication under this repository are covered by
the [W3C Code of Ethics and Professional Conduct][cepc].

## Working items

- Working draft of the core specification (written using [BikeShed][bikeshed])
  - source file: [./spec/identity/index.bs](./spec/identity/index.bs)
  - compiled file served as HTML:
    https://w3c.github.io/WebID/spec/identity/index.html

## Other relevant documents

- 2014 ED of the core specification (written using [ReSpec][respec])
  - source file: 
    [./spec/drafts/ED-webid-20140305/identity/index.html][2014ED]
  - source file served as HTML:
    https://w3c.github.io/WebID/spec/drafts/ED-webid-20140305/identity/index.html

[respec]: https://respec.org/docs/
[bikeshed]: https://speced.github.io/bikeshed/
[2014ED]: ./spec/drafts/ED-webid-20140305/identity/index.html
[BUILD.md]: ./BUILD.md
[workflow]: ./.github/workflows/bikeshed.yml
[cepc]: https://www.w3.org/Consortium/cepc/