<h1 align="center">👨‍💻 Epitech Criterion Actions</h1>

<p align="center">Simple GitHub action for Criterion unit tests at Epitech</p>

<p align="center">
<a href="./LICENCE"><img alt="License" src="https://img.shields.io/badge/License-GPLv3-blue.svg" /><a>
<a href="https://github.com/Elnix90/EpitechCriterionActions/issues"><img alt="issues" src="https://badgen.net/github/issues/Elnix90/EpitechCriterionActions" /></a>
<a href="https://github.com/Elnix90/EpitechCriterionActions"><img alt="PRs" src="https://badgen.net/github/prs/Elnix90/EpitechCriterionActions" /></a>
<a href="https://github.com/Elnix90/EpitechCriterionActions"><img alt="Open Source" src="https://badges.frapsoft.com/os/v1/open-source.svg?v=103" /></a>
<a href="https://github.com/Elnix90/EpitechCriterionActions/network/members"><img alt="forks" src="https://badgen.net/github/forks/Elnix90/EpitechCriterionActions" /></a>
<a href="https://github.com/Elnix90/EpitechCriterionActions"><img alt="stars" src="https://badgen.net/github/stars/Elnix90/EpitechCriterionActions" /></a>
</p>

## 🔍 Description

Epitech Criterion Actions is a GitHub action that will automatically launch the unit tests create with [Criterion](https://criterion.readthedocs.io/en/master/index.html) in the same way as the Epitech autocorrector. One the action is incorporated into the project, it will start when changes are sent to the main branch of the project. The results are formatted and sent to a special branch named "epitech-criterion-action" ( [see branch on example project](https://github.com/MaximePremont/EpitechCriterionActions_Example/tree/epitech-criterion-actions) )

## 💻 Example

### An example project has been created: [Elnix90/epitech-template](https://github.com/Elnix90/epitech-template)

![Example](./example.png?raw=true "Example")
<p align="center">README.md of epitech-criterion-actions branch</p>

## ⚠️ Requirements

The criterion unit tests and the project must be organized as indicated in the epitech unit tests documentation.

#### The main points are :

- Have your Makefile at the root of the repository
- Have a the following "tests_run" rule:

```Makefile
tests_run: unit_tests
	rm -f $(GCDA)
	./$(UNIT_TESTS)
	gcovr --gcov-executable "llvm-cov gcov" --exclude tests/ > eca_lc
	cat eca_lc
	gcovr --gcov-executable "llvm-cov gcov" --exclude tests/ --txt-metric branch > eca_lb
	cat eca_lb
```

- The test executable must be called "unit_tests"
- The test executable must not be deleted when calling "tests_run" in the makefile

> Do not hesitate to take a look at [the sample project](https://github.com/MaximePremont/EpitechCriterionActions_Example) to see how to correctly build your project and Makefile.

##

Create a `.github/workflows/unit_test.yaml` workflow file in your project repository :

```yaml
name: Unit tests

on:
    push:
        branches:
            - main

permissions:
    contents: write

jobs:
    unit_test:
        runs-on: self-hosted
        steps:
            - uses: Elnix90/EpitechCriterionActions@master
```

If you have any questions or problems, you can [create an issue](https://github.com/Elnix90/EpitechCriterionActions/issues).

Do you have the slightest idea or do you want to develop the project? **Feel free to contribute !** For this a [contribution guide](./CONTRIBUTING.md) is available.

Do not hesitate to use this GitHub Action for your projects and your reviews !

#### Don't forget to leave a star if the project was useful to you :star:

> [Epitech Criterion Actions](https://github.com/Elnix90/EpitechCriterionActions) by [Maxime Premont](http://github.com/MaximePremont), reborn by [Elnix90](http://github.com/Elnix90)
