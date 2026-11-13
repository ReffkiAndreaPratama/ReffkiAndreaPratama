# Profile Automation

This repository uses GitHub Actions for two optional profile-maintenance tasks.

## Recently updated repositories

Workflow: [refresh-profile.yml](../.github/workflows/refresh-profile.yml)

- Schedule: daily at 06:17 UTC (13:17 WIB).
- Manual trigger: available through the Actions tab using the workflow named Refresh profile repository activity.
- Behaviour: reads public repositories owned by this account, excludes forks and the profile repository itself, then updates the marked recent-repositories table in README.md.
- Permissions: repository contents write access is required to commit the refreshed README.

The workflow checks for both README markers before changing the file. If either marker is missing, it stops instead of replacing unrelated content.

## Contribution snake

Workflow: [snake.yml](../snake.yml)

- Schedule: every 12 hours.
- Triggers: pushes to the main branch and manual dispatch.
- Behaviour: generates contribution-graph SVG files and publishes them to the output branch.

The generated images are an optional visual extra; they are not a measure of engineering ability or project quality.

## Troubleshooting

1. Open the repository's Actions tab.
2. Select the workflow and inspect the latest run.
3. Read the failed step's log.
4. Confirm the workflow has the required repository permissions.
5. For the recent-repository updater, verify that the README marker comments still exist.

Automations may be delayed by GitHub Actions availability and do not guarantee that every third-party profile widget will load.
