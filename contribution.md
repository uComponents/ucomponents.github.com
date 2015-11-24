---
layout: default
title: Contribution and Development
---

# Contributing

Want to contribute to uComponents? Great!

There are a few ways to contribute to the uComponents project:

* Raising bugs - [Create a new issue](https://github.com/uComponents/uComponents/issues) and we'll investigate further.
* Submitting patches (or new features) - [Create a fork of the repository](https://github.com/uComponents/uComponents/fork), and make a pull request.
* Discussing ideas - [Start a new discussion thread](https://github.com/uComponents/uComponents/issues).

For general support, please use the [uComponents forum](http://our.umbraco.org/projects/backoffice-extensions/ucomponents/questionssuggestions) on Our Umbraco community website.

---

# Development

The uComponents team use Git source-control for our repository.

If you are new to Git, please take time to read the guide: [Using Git on GitHub](https://help.github.com/articles/set-up-git).

## Clone the repository

To clone the uComponents project from GitHub, use the following command:

	git clone https://github.com/uComponents/uComponents.git

Once the repository has been cloned, your local working directory will be using the `master` branch. To switch to the latest development branch, use the following command:

	git checkout develop

## Branches

Our branching structure is as follows:

| Branch | Comment |
|--------|---------|
| [master](https://github.com/uComponents/uComponents/tree/master) | This branch contains the source-code for the latest stable release. |
| [develop](https://github.com/uComponents/uComponents/tree/develop) | The latest development branch of the stable code-base, currently the v6.x releases of uComponents, which support Umbraco 6.0+ (on .NET 4.0). |

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

These components are still available in uComponents, accessible in the `uComponents.Legacy` assembly.

---

## Umbraco compatibility

Details on uComponents compatibility with specific Umbraco versions, please see our [Umbraco compatibility grid](/compatibility/).
