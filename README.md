# gisce/commitlint-rules

This package provides a custom set of rules for commit messages in all GISCE projects and libraries, ensuring consistency and readability. It extends the conventional commit message guidelines with specific customizations suitable for our workflow.

## Installation

To use `gisce/commitlint-rules` in your project, first install the package along with `commitlint`:

```bash
npm install --save-dev @commitlint/cli @gisce/commitlint-rules
```

## Configuration

After installation, create a `commitlint.config.js` file in the root of your project with the following content:

```js
module.exports = {
  extends: ["@gisce/commitlint-rules"],
};
```

This configuration extends the custom rules defined in `@gisce/commitlint-rules`.

## Rules

The custom rules defined in this package are as follows:

- `body-max-line-length`: Set to always ignore the line length in the commit message body.
- `footer-max-line-length`: Set to always ignore the line length in the commit message footer.

These rules are built on top of the conventional commit rules provided by [`@commitlint/config-conventional`](https://github.com/conventional-changelog/commitlint/tree/master/%40commitlint/config-conventional).


## Usage

Commit messages in projects using this package will be checked against the defined rules. Ensure your commit messages are structured according to these rules to maintain consistency across GISCE's codebases.

| Commit message                                                                                                                                                                                   | Release type                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------- |
| `fix(pencil): stop graphite breaking when too much pressure applied`                                                                                                                             | ~~Patch~~ Fix Release                                                                                           |
| `feat(pencil): add 'graphiteWidth' option`                                                                                                                                                       | ~~Minor~~ Feature Release                                                                                       |
| `perf(pencil): remove graphiteWidth option`<br><br>`BREAKING CHANGE: The graphiteWidth option has been removed.`<br>`The default graphite width of 10mm is always used for performance reasons.` | ~~Major~~ Breaking Release <br /> (Note that the `BREAKING CHANGE: ` token must be in the footer of the commit) |

## Cheat Sheet: Commit Message Types

| Type      | Category                 | Description                                              |
|-----------|--------------------------|----------------------------------------------------------|
| `feat`    | Features                 | A new feature.                                           |
| `fix`     | Bug Fixes                | A bug fix.                                               |
| `docs`    | Documentation            | Documentation only changes.                              |
| `style`   | Styles                   | Changes that do not affect the meaning of the code.      |
| `refactor`| Code Refactoring         | A code change that neither fixes a bug nor adds a feature.|
| `perf`    | Performance Improvements | A code change that improves performance.                 |
| `test`    | Tests                    | Adding missing tests or correcting existing tests.       |
| `build`   | Builds                   | Changes that affect the build system or external dependencies. |
| `ci`      | Continuous Integrations  | Changes to CI configuration files and scripts.           |
| `chore`   | Chores                   | Other changes that don't modify src or test files.       |
| `revert`  | Reverts                  | Reverts a previous commit.                               |



## Contributing

Contributions to the `gisce/commitlint-rules` package are welcome. If you have suggestions for improving or extending the rules, please open an issue or a pull request in the repository.

## License

MIT