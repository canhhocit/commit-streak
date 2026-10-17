# Commit streak

This repository uses GitHub Actions to make one batch of commits per day.

## Daily schedule

The workflow runs at 00:15 Vietnam time (17:15 UTC). It makes:

- 11–19 commits on days 1–9 (day of month + 10)
- A number of commits equal to the day of month on days 10–31

For example, day 5 makes 15 commits; day 17 makes 17 commits. You can also start it manually from the Actions tab with **Daily commit streak → Run workflow**.

Each commit appends one line to `activity.log`. The workflow needs repository write permission, configured in the workflow with `permissions: contents: write`.

## Setup after connecting the GitHub repo

1. Push this folder and its `.github/workflows/daily-commits.yml` file to the repository's default branch.
2. In GitHub, open **Settings → Actions → General → Workflow permissions** and allow read and write permissions if the organization/repository policy requires that setting.
3. Confirm the workflow appears under **Actions** and that scheduled workflows are enabled.

GitHub scheduled runs can be delayed during high load. The commits are given Vietnam-local timestamps so GitHub can associate them with the intended local date.
