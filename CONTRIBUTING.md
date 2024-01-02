# Contributing Guide

Thank you for investing your time in contribution to WebID!

The [w3c/WebID](https://github.com/w3c/WebID) repository contains the source
code of the work on WebID specifications of the [W3C WebID
Group](https://www.w3.org/groups/cg/webid/) (CG).

Work includes specifications, use cases and requirements, best practices and
guidelines, primers and notes about WebID and ecosystem.

## Code of conduct

Read the [Positive Work Environment at W3C: Code of Ethics and Professional
Conduct](https://www.w3.org/Consortium/cepc/) to keep our community
approachable and respectable.

See [additional
resources](https://www.w3.org/about/positive-work-environment/#Education) for
education and training to promote a positive work environment.

## Conformance

The key words “MUST” and “MUST NOT” are to be interpreted as described in [BCP
14](https://tools.ietf.org/html/bcp14)
[RFC2119](https://datatracker.ietf.org/doc/html/rfc2119)
[RFC8174](https://datatracker.ietf.org/doc/html/rfc8174) when, and only when,
they appear in all capitals, as shown here.

## Contributions

In order to be a substantive contributor to work items, you MUST be a member of
the CG. It’s easy to [join the CG](https://www.w3.org/community/webid/join) if
you’d like to contribute. People agree to the [W3C Community License Agreement
(CLA)](http://www.w3.org/community/about/agreements/cla/) upon joining the CG.

We accept different types of contributions as described below.

To ensure that anyone can follow along a contribution and support
verification, provide citations to significant units of information, e.g.,
references to specific requirements in technical reports, decisions made in a
formal meeting. To promote accountable discourse, request citations when
questioning uncited claims.

### Discussions

If you'd like help troubleshooting a pull request (PR) you're working on, have
a great new idea, or want to share implementation feedback, join us in this
repository or on the public-webid@w3.org mailing list.

### Issues

[Issues](https://docs.github.com/en/github/managing-your-work-on-github/about-issues)
are used to track tasks that contributors can help with. If an issue has a
triage label, we haven't reviewed it yet and so you are not encouraged to
begin work on it.

If you've found something in the content or the website that might need to be
updated, search open issues to see if someone else has reported the same
thing. If it's something new, open an issue. We'll use the issue to have a
conversation about the problem you want to fix.

### Pull requests

A [pull
request](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests)
is a way to suggest changes in our repository.

### Translations

We aim to have our documents internationalized and available in multiple
languages. The source content in the [w3c/WebID](https://github.com/w3c/WebID)
repository is written in English. We accept contributions to localize the
English content.


## Contributions at source repository

It is strongly encouraged that any issues and PRs are made at their source.

A low-barrier way to add concrete suggestions is to submit a use case or a
user story. User stories are descriptions of desired features written in a
special way. User stories might then be used when formulating use cases and
requirements.


## Creating and solving issues

### Create a new issue

If you spot a problem with the technical reports being worked on in this
repository or would like to request a feature, [search if an issue already
exists](https://docs.github.com/en/github/searching-for-information-on-github/searching-on-github/searching-issues-and-pull-requests#search-by-the-title-body-or-comments).
If a related issue doesn't exist, you can open a new issue. In the issue,
include relevant information that can help others, e.g., links to
specifications, issues, implementations, test suite, discussions.

### Solve an issue

Scan through our [existing
issues](https://github.com/w3c/WebID/issues/) to find one that
interests you. You can narrow down the search using `labels` as filters. See
[Labels](https://github.com/github/docs/blob/main/contributing/how-to-use-labels.md)
for more information. If you find an issue to work on, you are welcome to open
a PR with a fix.


## Make changes

### Make changes locally

1. Install Git
2. Fork the repository.
3. Create a working branch and start with your changes!


## Commit your update

Commit the changes once you are happy with them. See [Atom's contributing
guide](https://github.com/atom/atom/blob/master/CONTRIBUTING.md#git-commit-messages)
to know how to use emoji for commit messages.

Once your changes are ready, don't forget to [self-review](#self-review) to
speed up the review process:zap:.

### Self-review

You are strongly encouraged to review your own PR first.

For content changes, make sure that you:

* [ ] Confirm that the changes meet the user experience and goals outlined in
  the content design plan (if there is one).
* [ ] Compare your PR's source changes to staging to confirm that the
  output matches the source and that everything is rendering as expected. The
  W3C service to [creating diff between HTML pages](https://services.w3.org/htmldiff)
  can also be used.
* [ ] Review the content for technical accuracy.
* [ ] Review the content using the [translation guide for
  writers](https://github.com/github/docs/blob/main/contributing/translations-for-writers.md)
  and the [W3C Manual of Style](https://www.w3.org/2001/06/manual/) as guides.
* [ ] Review the content to use [inclusive
  language](https://github.com/github/docs/blob/main/contributing/content-style-guide.md#inclusive-language).
  Celebrate people/names from under represented ethnic/cultural backgrounds in
  examples, e.g., [unique forenames in
  Earth](https://forebears.io/earth/forenames), [example person
  names](https://developers.google.com/style/examples#example-person-names).
* [ ] If there are any failing checks in your PR, troubleshoot them until
  they're all passing.
* [ ] Follow the [Publication Rules](#publication-rules)


## Creating a pull request

When you're finished with the changes to documents that are maintained in this
repository, create a PR.

* Include atomic commits, small PRs: "one concern, one PR".
* In the PR comment, provide as much context and evidence to help reviewers
  evaluate the PR. Identify, classify, describes the changes as per W3C
  Process [Correction
  Classes](https://www.w3.org/Consortium/Process/#correction-classes).
* Don't forget to [link PR to
  issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue)
  if you are solving one.
* We can ask for changes to be made before a PR can be merged, either using
  [suggested
  changes](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/incorporating-feedback-in-your-pull-request)
  or PR comments. You can apply suggested changes directly through the UI. You
  can make any other changes in your fork, then commit them to your branch.
* As you update your PR and apply changes, mark each conversation as
  [resolved](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/commenting-on-a-pull-request#resolving-conversations).
* If you run into any merge issues, checkout this [git
  tutorial](https://lab.github.com/githubtraining/managing-merge-conflicts) to
  help you resolve merge conflicts and other issues.
* You can attribute a commit to more than one author by adding one or more
  `Co-authored-by: NAME <NAME@EXAMPLE.COM>` per line to commit's message
  (after two empty lines). See [github
  tutorial](https://docs.github.com/en/pull-requests/committing-changes-to-your-project/creating-and-editing-commits/creating-a-commit-with-multiple-authors).

### Your PR is merged!

Congratulations :tada: WebID community thanks you :sparkles:.


## Work items

In general, all documents in scope of the group are welcome. Work items can be
documents or software.

### New work item proposal

* Propose new work item as an issue in https://github.com/w3c/WebID
  and propose it as an agenda topic in a group meeting.
* Include publicly accessible link to abstract or draft.
* List and link to owners (at least 1 person for advancing the work item and 1
  other person).
* Answer the following questions in order to document how you are meeting the
  requirements for a new work item at the W3C WebID Community Group. Please
  note if this work item supports certain programs or another government or
  private sector project.
  1. Explain what you are trying to do, using no jargon or acronyms.
  2. How is it done today, and what are the limits of the current practice?
  3. What is new in your approach, and why do you think it will be successful?
  4. How are you involving participants from multiple skill sets and global
     locations in this work item? (Skill sets: technical, design, product,
     marketing, anthropological, and UX. Global locations: Africa, the
     Americas, APAC, Europe, Middle East, Antarctica.)
  5. What actions are you taking to make this work item accessible to a
     non-technical audience?


## Publication Rules

W3C CG reports are not required to follow the publication requirements as W3C
reports [on the standards track](https://www.w3.org/TR/). However, we
recommend using the [W3C's Publication rules for Recommendation
(“REC”)](https://www.w3.org/pubrules/doc/rules/?profile=REC) as a guideline.
WebID CG's technical reports differ along the lines of document status,
rights, identifiers. To help readers already familiar with W3C technical
reports, it is recommended to maintain the same look and feel.

See also the [W3C Manual of Style](https://www.w3.org/2001/06/manual/)
guide containing best current practice, written for editors and authors of W3C
technical reports.

We also make the following recommendations:

* MUST be a valid HTML5 document (see also the [W3C Markup Validation
  Service](https://validator.w3.org/)).
* MUST include published and modified dates (`YYYY-MM-DD`).
* Follow the [Internationalization Best Practices for Spec
  Developers](https://www.w3.org/TR/international-specs/).
* Follow the [Linked Data](https://www.w3.org/DesignIssues/LinkedData) design
  principles. Give all significant units of information, e.g., concepts,
  requirements, an identifier, and provide a description using a concrete RDF
  syntax (see also [Spec Terms](http://www.w3.org/ns/spec)).
* Cite the source resource in which consensus was reached for a given
  statement.
* Changelog from previous published releases (if applicable).
* Considerations section, e.g., [Self-Review Questionnaire: Security and
  Privacy](https://www.w3.org/TR/security-privacy-questionnaire/),
  Accessibility, Internationalization, Societal Impact.
* Conformance Classes section to identify who and/or what will implement the
  specification.
* Document wilful violations.
* Use consistent spelling throughout the document.


## Decisions

Also see https://www.w3.org/Consortium/Process/#decisions for general guidance.

### Processing pull requests

Unless there is a prior CG decision otherwise, changes to TRs use the W3C Process [Correction Classes](https://www.w3.org/Consortium/Process/#correction-classes) as follows:

|Correction Class|Requirements|Time|
|-|-|-|
|[No changes to text content](https://www.w3.org/Consortium/Process/#class-1)|Editors MAY PR and/or merge at their discretion.|Within 5 days or 2 meetings.|
|[Changes that do not functionally affect interpretation of the document](https://www.w3.org/Consortium/Process/#class-2)|Editors SHOULD PR and/or merge at their discretion.|Within 5 days or 2 meetings.|
|[Other changes that do not add new features](https://www.w3.org/Consortium/Process/#class-3)|MUST PR.|Within 10 days or 2 meetings.|
|[New features](https://www.w3.org/Consortium/Process/#class-4)|MUST PR.|Within 10 days or 2 meetings.|
|[Changes to the contents of a registry table](https://www.w3.org/Consortium/Process/#class-5)|Editors or chairs MUST PR.|Within 10 days or 2 meetings.|


## Vocabulary Management

The policy for the management of vocabularies under the W3C namespace is
described in [Adding to W3C RDF
Namespaces](https://www.w3.org/2016/08/namespaces/) as well as
[w3c/ns](https://github.com/w3c/ns).


## Meetings

TBD.


## Communication

The opinions of CG members may carry particular weight, whether they are
expressed within our community or elsewhere. As a CG member:
* It is assumed you are speaking as an individual unless you state otherwise.
* If you want to express the opinion of your organisation or a group you are
  affiliated with, make it clear before you state their view.
* Do not use phrases like "on behalf of the CG" or "the CG thinks that" unless
  the group has asked you to do so.
* When communicating CG decisions, provide references to what was decided and
  what was not decided.
