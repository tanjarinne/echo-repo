<h1 align="center">Echo</h1>
<div align="center">
    <i>Echo is a service that responds with any header or body you send over, as-is.</i>
</div>
<br>

## About

This project is intended to be educational, for-research-only and solving a fictional problem, and is not intended to work on any production environment whatsoever as it can potentially leak private information due to its most basic functionality.

Echo is written in several different programming languages, each tracked in a separate repository, aiming to follow code conventions, best practices, etc., and implementing the testing / running / deploying specific tool-chains for a given language and their stacks.

That arises a problem of maintainability as its complexity grows as many languages are used.

<p align="center">Enter <code>repo</code>.</p>

[Android's Repo](https://source.android.com/setup/develop/#repo) solves that problem by providing a command line tool that aggregates git repositories in an xml document, allowing to handle them in groups as they were a single one.

It comes with caveats though.

Repo will clone all repositories in a detached mode by default – albeit setting `master` as the main branch. This can be easily amended by checking out `master` –or any other branch– the first time each repository is used.

## Requirements

* Repo

#### Installing Repo

##### Mac OS

```bash
$ brew install repo
```

## Repositories index

| Repository | Language |
|-|-|
| [`echo-crystal`](https://github.com/catsandfoxes/echo-crystal) | [Crystal](https://crystal-lang.org/) |

## Cloning (initialising in `repo` terms)

`repo init` follows the same structure than `git clone`:

```bash
$ repo init -u git@github.com:catsandfoxes/echo-repo.git echo
$ cd echo
$ repo sync
Fetching project echo-repo
...

```

This will create an `echo` folder, fetch the xml manifest from this repository and initialise Repo within, then, afterwards, `repo sync` will fetch the latest change from each repository into their own folder.


## Common operations

Each repository provides a Makefile to perform common standard-named operations.

They can be invoked in all repositories at once (not in parallel), using `repo forall`:

| Make target | Example |
|-|-|
| `test` | <pre>$ repo forall -c 'make test'<br></pre> |

## Authors

Cats & Foxes 2018
