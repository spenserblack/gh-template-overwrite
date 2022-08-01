# `gh template-overwrite`

This extension will overwrite your *current files* with the contents from a
template repository

## Why?

My use case was that I wanted to do a major change to the implementation of an
existing project, and wanted to use a template repository to ease the initial
setup of the new implementation.

## Usage

```bash
gh template-overwrite <user>/<repo>
git commit -m "Initial commit of new implementation"
```

## How it works

This extension creates a remote repository called `template`. It then removes
all tracked files, fetches `template` and gets its default branch from the API,
and does `git reset --soft template/<default>`.
