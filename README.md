# Shared Mergify policy

Consumers in this GitHub owner use `extends: mergify-config` in their Mergify configuration. Repository-specific checks and queue behavior remain in each consumer. Mergify Merge Protections must be a required GitHub check, bound to the Mergify app (10562).

Open SWE review is temporarily paused under MOB-1461. The shared rule still rejects drafts. To restore review, unsuspend the Open SWE installation first, uncomment the Open SWE check conditions in `.mergify.yml`, validate a consumer canary, and merge the policy change. Refresh existing consumer pull requests and verify their Mergify results; do not assume every existing PR is reevaluated immediately.

The source excludes itself from Open SWE review so policy can be restored without a circular dependency. Changes to this repository require deliberate review. Never add application-specific CI requirements here. Do not put secrets or private repository details in a public source.

Mergify supports one level of same-owner inheritance. Local rules with the same name override inherited rules; do not shadow the shared policy names. Shared YAML anchors do not cross configuration files.

Linear: MOB-1461
