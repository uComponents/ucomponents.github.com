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

The uComponents team use Git source-control for our repository.

If you are new to Git, please take time to read the guide: [Using Git on GitHub](https://help.github.com/articles/set-up-git).

## Clone the repository

To clone the uComponents project from GitHub, use the following command:

	git clone https://github.com/uComponents/uComponents.git

Once the repository has been cloned, your local working directory will be using the `master` branch. To switch to the latest development branch, use the following command:

	git checkout dev-6.0.1

## Branches

Our branching structure is as follows:

| Branch | Comment |
|--------|---------|
| [master](https://github.com/uComponents/uComponents/tree/master) | This branch contains the source-code for the latest stable release. |
| [7.x](https://github.com/uComponents/uComponents/tree/dev-7.x) | The source-code for the upcoming v7.x release of uComponents, which will support Umbraco 7.0+ (on .NET 4.5). |
| [6.x](https://github.com/uComponents/uComponents/tree/dev-6.x) | The source-code for the current stable v6.x releases of uComponents, which will support Umbraco 6.0+ (on .NET 4.0). |
| [<s>5.x</s>](https://github.com/uComponents/uComponents/tree/dev-5.x) | <s>The source-code for the 'legacy' v5.x versions of uComponents, which supports Umbraco 4.8+ (on .NET 4.0).</s> |
| [<s>4.x</s>](https://github.com/uComponents/uComponents/tree/dev-4.x) | <s>The source-code for the 'legacy' v4.x versions of uComponents, which supports Umbraco 4.7.1 (on .NET 4.0).</s> |
| [<s>3.x</s>](https://github.com/uComponents/uComponents/tree/dev-3.x) | <s>The source-code for the 'legacy' v3.x versions of uComponents, which supports Umbraco 4.5.2 (on .NET 3.5).</s> |


The current developments for upcoming releases are available in their own branches.

| Branch | Comment |
|--------|---------|
| [dev-7.0.0](https://github.com/uComponents/uComponents/tree/dev-7.0.0) | The latest bleeding-edge code-base for upcoming _new_ features. |
| [dev-6.0.1](https://github.com/uComponents/uComponents/tree/dev-6.0.1) | The latest development branch of the stable code-base. |

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

For Umbraco v6.2.0 _([pending approval of pull-request](https://github.com/umbraco/Umbraco-CMS/pull/133))_

* Url Picker
* Multi-Url Picker

These components are still available in uComponents, accessible in the `uComponents.Legacy` assembly.

---

## Umbraco compatibility

Details on uComponents compatibility with specific Umbraco versions, please see our [Umbraco compatibility grid](/compatibility/).
