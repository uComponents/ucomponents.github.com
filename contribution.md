---
layout: default
title: Contribution and Development
---

# Contributing

Want to contribute to uComponents? Great!

There are a few ways to contribute to the uComponents project:

* Raising bugs - [Create a new workitem](http://ucomponents.codeplex.com/WorkItem/Create) and we'll investigate further.
* Submitting patches (or new features) - [Create a fork of the repository](http://ucomponents.codeplex.com/SourceControl/network/create/fork), and make a pull request.
* Discussing ideas - [Start a new discussion thread](http://ucomponents.codeplex.com/discussions/create).

For general support, please use the [uComponents forum](http://our.umbraco.org/projects/backoffice-extensions/ucomponents/questionssuggestions) on Our Umbraco community website.

---

# Development
The uComponents team use Mercurial source-control as our repository.

If you are new to Mercurial, please take time to read the guide: [Using Mercurial on CodePlex](http://codeplex.codeplex.com/wikipage?title=Using%20TortoiseHG%20with%20CodePlex&referringTitle=Source%20control%20clients&ProjectName=codeplex).

## Clone the repository

To clone the uComponents project in Mercurial, use the following command:

	hg clone https://hg.codeplex.com/ucomponents

Once the repository has been cloned, your local working directory will be using the `default` branch. To switch to the latest development branch, use the following command:

	hg update 5.4.2-dev

## Branches

Our branching structure is as follows:

| Branch | Comment |
|--------|---------|
| [default](http://ucomponents.codeplex.com/SourceControl/list/changesets?branch=default) | This branch does not contain any source-code. It is used as a meta-data branch for details on how to contribute, tagging and author credits. |
| [6.x](http://ucomponents.codeplex.com/SourceControl/list/changesets?branch=6.x) | The source-code for the upcoming v6.x release of uComponents, which will support Umbraco 6.0+. |
| [5.x](http://ucomponents.codeplex.com/SourceControl/list/changesets?branch=5.x) | The source-code for the current stable v5.x releases of uComponents, which supports Umbraco 4.8+ (on .NET 4.0). |
| [<s>4.x</s>](http://ucomponents.codeplex.com/SourceControl/list/changesets?branch=4.x) | <s>The source-code for the 'legacy' v4.x versions of uComponents, which supports Umbraco 4.7.1 (on .NET 4.0).</s> |
| [<s>3.x</s>](http://ucomponents.codeplex.com/SourceControl/list/changesets?branch=3.x) | <s>The source-code for the 'legacy' v3.x versions of uComponents, which supports Umbraco 4.5.2 (on .NET 3.5).</s> |


The current developments for upcoming releases are available in their own branches.

| Branch | Comment |
|--------|---------|
| [6.0.0-dev](http://ucomponents.codeplex.com/SourceControl/list/changesets?branch=6.0.0) | The latest bleeding-edge code-base for upcoming _new_ features. |
| [5.4.2-dev](http://ucomponents.codeplex.com/SourceControl/list/changesets?branch=5.4.2-dev) | The latest development branch of the stable code-base. |

---

## Semantic Versioning Specification
We aim to use SemVer for our version numbering system. For more information about SemVar, please see: <http://semver.org/>

---

## Components migrated to the Umbraco

The following parts of uComponents have been migrated to the core Umbraco release.

For Umbraco v4.8.0:

* Multi-Node Tree Picker
* Multiple Textstring
* Slider
* XPath CheckBoxList
* XPath DropDownList
* uQuery

For Umbraco v4.9.0:

* (Multi)Picker Relations

For Umbraco v6.1.0 _(pending approval)_

* Url Picker
* Multi-Url Picker

These components are still available in uComponents, accessible in the `uComponents.Legacy` assembly.

---

## Umbraco compatibility

Details on uComponents compatibility with specific Umbraco versions, please see our [Umbraco compatibility grid](/compatibility/).