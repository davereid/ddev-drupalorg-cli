# ddev-drupalorg-cli

DDEV add-on that installs the drupalorg CLI in the web container (`web-build/Dockerfile.drupalorg-cli`).

## Commits and releases

- release-please (`.github/workflows/release-please.yml`) makes releases from commit messages on `main`, so write them as [conventional commits](https://www.conventionalcommits.org/): `fix:` (patch), `feat:` (minor), `feat!:` or a `BREAKING CHANGE:` footer (major), and `docs:`, `test:`, `ci:` or `chore:` for changes that don't need a release. Commits without a type are left out of releases.
- Pull request titles follow the same format, since squash merges use them as the commit message. `.github/workflows/pr-title.yml` checks them.
- Don't edit `CHANGELOG.md` or `version.txt` by hand: release-please maintains them.

## Tests

- `tests/test.bats` installs the add-on in a temporary DDEV project and checks `drupalorg --version`. Run on the host (they need DDEV), skipping the test of the published release: `bats ./tests/test.bats --filter-tags '!release'`.
- Add or update a test when changing what the add-on installs or how versions are chosen.
