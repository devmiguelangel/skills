---
name: conventional-commits
description: Generate or revise Git commit messages using Conventional Commits whenever drafting a commit message or preparing a commit.
---

# Conventional Commits

Always use Conventional Commits when generating commit messages.

## Message format

```text
<type>(<optional scope>): <description>
```

Omit the parentheses when there is no scope.

- Choose one of: `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`, `revert`.
- Keep the entire subject line lowercase, with no period at the end and at most 72 characters, including the type, scope, and punctuation.
- Describe the concrete change. Never use vague descriptions such as `update` or `fix bug`.
- Mark breaking changes with `!` immediately before the colon, after the type and any scope, or add a `BREAKING CHANGE:` footer after a blank line. Explain the breaking change in the footer when using one. Preserve this uppercase footer label as an exception to the lowercase rule.

## Drafting a message

Use the supplied change description or diff to select the type, scope, and description. When preparing a commit from a repository, inspect the staged changes to determine what the commit contains. If the change is unclear, obtain enough context to describe it accurately.

Use a scope only when it identifies the affected component. Before returning the message, check its type, specificity, casing, length, punctuation, and any breaking-change marker.

## Examples

```text
feat(auth): add oauth2 login support
fix(api): handle empty search results
docs: document local setup
feat(api)!: require tokens for all endpoints
```

A breaking change with a footer:

```text
feat(api): require tokens for all endpoints

BREAKING CHANGE: unauthenticated requests now receive a 401 response
```
