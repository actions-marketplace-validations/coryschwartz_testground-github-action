# testground-github-action


## depreciated

A fork of this repo has been created and it has some much-needed improvements.
Please consider using this fork:

https://github.com/testground/testground-github-action 


Submit jobs to [testground](https://testground.ai) and view the outcome in Github.


## usage:

As a code checker for PRs:

```
---
name: Testground PR Checker

on: [push]

jobs:
  testground:
    runs-on: ubuntu-latest
    name: ${{ matrix.composition_file }}
    strategy:
      matrix:
        include:
          - backend_addr: <testground_daemon>
            backend_proto: <http/https>
            plan_directory: </path/to/testplan/directory>
            composition_file: </path/to/composition.toml
    steps:
      - uses: actions/checkout@v2
      - name: ${{ matrix.composition_file }}
        id: 
        uses: coryschwartz/testground-github-action@v1.0
        with:
          backend_addr: ${{ matrix.backend_addr }}
          backend_proto: ${{ matrix.backend_proto }}
          plan_directory: ${{ matrix.plan_directory }}
          composition_file: ${{ matrix.composition_file }}

```
