# `gh template-overwrite`

This extension will overwrite your *current files* with the contents from a
template repository

:warning: This will *not* commit any changes. Review the tracked changes before
committing.

## Why?

My use case was that I wanted to do a major change to the implementation of an
existing project, and wanted to use a template repository to ease the initial
setup of the new implementation.

## Usage

```bash
git checkout -b refactor/new-implementation
gh template-overwrite <user>/<repo>
git commit -m "Initial commit of new implementation"
```

## How it works

This extension creates a remote repository called `template`. It fetches
`template` and gets its default branch from the API, untracks the
current files, and does `git checkout template/<default> -- .`.
