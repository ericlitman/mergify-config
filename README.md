# Shared Mergify configuration

Repositories owned by `ericlitman` can import these defaults with:

```yaml
extends: mergify-config
```

The shared file sets a serial queue, one parallel check, and GitHub check-run
reporting without PR comments. Each consumer owns its queue rules, CI checks,
and review requirements. Importing these defaults alone does not enable
automatic merging.

Edit `.mergify.yml` here through a pull request, using GitHub or Mergify's config
editor. The repository owner administers this policy; no additional human
reviewer is required. Consumers read the default branch after the change merges.
Use `@mergifyio refresh` on an existing consumer PR to request reevaluation.

Mergify resolves `extends` within the same repository owner. Its app must have
access to the source. Public consumers need a public source. Only one extension
level is supported, and local values and same-name rules take precedence.

Repository-specific checks remain in the consumer configuration and GitHub
protections. Subscription coverage and product activation are managed separately
in Mergify.
