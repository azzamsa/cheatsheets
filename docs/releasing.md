# Release Checklist

- Run the release task: `./scripts/release.sh version=v<mayor.minor.path>`. Such `./scripts/release.sh v0.1.7`.
- Check if [Continuous Integration](https://github.com/azzamsa/cheatsheets/actions/workflows/ci.yml) workflow is completed successfully.
- Push the tags: `git push --tags`
- Wait for [Continuous Deployment](https://github.com/azzamsa/cheatsheets/actions/workflows/cd.yml) workflow to finish.
- Create a new GitHub release with the created tag above, and copy the release news from the CHANGELOG.md.
