# Semantic Release Action

[GitHub composite Action](https://docs.github.com/en/actions/creating-actions/creating-a-composite-action) for personal projects.

## Usage

Add new [GitHub Workflow](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions):

```yaml
name: Semantic Release
on:
  workflow_dispatch
jobs:
  release:
    name: Release
    runs-on: ubuntu-latest
    steps:
      - name: Custom semantic release
        uses: cogni8r/semantic-release-action@v2
        with:
          gpg-private-key: ${{ secrets.GPG_PRIVATE_KEY }}
          gpg-passphrase: ${{ secrets.GPG_PASSPHRASE }}
          github-token: ${{ secrets.BOT_TOKEN }}
          npm-token: ${{ secrets.NPM_TOKEN }}
          git-author-name: ${{ secrets.GIT_AUTHOR_NAME }}
          git-author-email: ${{ secrets.GIT_AUTHOR_EMAIL }}
```

Add repository secrets:

- `GPG_PASSPHRASE`
- `BOT_TOKEN`
- `GIT_AUTHOR_NAME`
- `GIT_AUTHOR_EMAIL`
- `NPM_TOKEN`
- `GPG_PRIVATE_KEY`
