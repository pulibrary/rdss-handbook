# Development Practice

## Routine / Project work

### Selecting an issue

Each week we either work from the [Sprint Board](https://app.zenhub.com/workspaces/rdss-61a4f1a12a399b001730f65a/board)
The `Sprint Backlog` column of a given board has issues ordered roughly by priority.
Always assign yourself to an issue before to starting to work on it, and move it
to the `in progress` column.

### Pairing

Our team considers ourselves "pairing-friendly." Several of us very much like to pair, and we all do pair at least sometimes. Feel free to ask anyone to pair with you if you would like help or just want some company to work on an issue.

If a PR is submitted by the pair, they can merge it themselves without code review. The idea is that code review has happened during the process of development with a pair. They can still request review if they'd like another opinion. 

Some recommended reading:
* [Slides about pairing best practices](https://docs.google.com/presentation/d/1-PhkB_uSPHrz4-eWI6R9AzLo1fGVWqcxMMdUlAWOvng/edit#slide=id.p)
* [On Pair Programming from martinfowler.com](https://martinfowler.com/articles/on-pair-programming.html#HowToPair)
* [How to get better at pair programming from thoughtbot](https://thoughtbot.com/blog/how-to-get-better-at-pair-programming) 

Checklist for every time you pair:
- [ ] Use an editor where you can both see the outline of the project.
- [ ] Turn on absolute line numbers. 
- [ ] Agree on task, scope, and intention. 
- [ ] Set a timer. Remember to take breaks and swap drivers.
- [ ] Keep the chat going. If you're driving, narrate what you're doing.
- [ ] Use Co-authored-by lines in the commit message (This [.gitmessage](https://github.com/pulibrary/pul-the-hard-way/blob/main/gitmessage.md) file might be handy)
- [ ] Check in afterwards about how it went. 

### Submitting code

* Ensure code is arranged in logical, unitary commits unless you want it squash-merged.
* Ensure any new or modified code has test coverage. Many of us practice test-driven development, but at the least a test should be confirmed to be failing before the code change is applied.
* Run Rubocop to enforce code style agreed upon by our team.
* Open a pull request in Github
  * Reference the relevant issues, using [github keywords](https://docs.github.com/en/enterprise/2.16/user/github/managing-your-work-on-github/closing-issues-using-keywords) if the issue will be resolved
* Make adjustments as-needed according to code review.
* If your PR isn't getting reviewed, freely post it in slack.
* If your PR is approved and passes CI checks you may merge your own pull request. Usually this happens when it's reviewed before CI is finished.
* If this code was developed in a pair and passes CI checks, you may merge without waiting for another reviewer.
* Ensure the issue is closed if no further work is required.

### Reviewing code

* Review other pull requests over the course of the day.
* We generally follow the [Samvera Code Review](https://samvera.github.io/review.html) guidelines
* Ask the author of the code to pair with you on the review if desired / required.
* We generally want code to be merged, but feel free to ask questions about code you do not understand.

## Dependabot

We have set up our github repositories to use Dependabot, which generates PRs to upgrade dependencies based on security warnings. Based on our experience with these PRs it is important to test a deployment to a staging server before merging them even if the tests are all passing. Also, in some of our projects our tests do not fully cover our javascript code. In those cases when javascript dependencies are updated it can be helpful to do a bit of QA before merging.

If the PR has been open for a while, or you've just merged another PR, use the `@dependabot rebase` comment to trigger a rebase before deploying. This can take a few minutes.

## Ruby Documentation (Using YARD)

Code documentation is implemented for Ruby code bases using [YARD](https://yardoc.org/), a Gem which parses Ruby source code file comments and generates documentation in the HTML.

### Installing the Gem

```bash
$ bundle add --group "development" yard
```

### YARD Tags

YARD using a system of tags invoked from within the comments of a source code file by prefixing the tag keyword with the `@` character. The comprehensive list of tags is available [here](https://rubydoc.info/gems/yard/file/docs/Tags.md).

### Examples

For documenting `class` implementations, one may look to the following example for guidance:

```ruby
# @class My Class Description
class MyWebServer
  # @!attribute state
  #   @return [Numeric] the number of POST requests received by the server
  attr_accessor :name

  # Handles a request
  # @param request [Request] the request object
  # @param [Hash] opts the options to create a message with.
  # @option opts [String] :foo The foo argument
  # @option opts [Array<String>] :bar The bar argument
  # @return [String] the resulting webpage
  def get(request, opts = {})
    "GET request received"
  end

  # (see #get)
  # @note This method may modify our application state!
  # @param (see #get)
  # @return (see #get)
  def post(request, opts = {})
    @state += 1
    "POST request received"
  end
end
```

### Generating YARD Documentation

Please generate the documentation with the following invocation:

```bash
$ bundle exec yard doc
$ open doc/index.html
```

## Styling with Prettier

Prettier is a tool used for enforcing source code and configuration formatting standards.

In order to integrate Prettier into any given project, the following are required to already be installed in your project:

- [Node.js](https://nodejs.org/en/)
- [Yarn](https://yarnpkg.com/)

### Installing [Prettier](https://prettier.io/)

```bash
yarn add -D eslint-config-prettier
yarn add -D prettier eslint-config-prettier
```

### Configuring Prettier

Prettier configuration options are set within a YAML file `.prettierrc`, which should be located at the root path of the project.

The following configuration defines a default minimal configuration which prefers double quotes to single quotes:

```yaml
singleQuote: true
overrides: []
```

More information on Prettier configuration can be found [within the documentation](https://prettier.io/docs/configuration/).

#### Configuring Prettier to Ignore File Paths

Please note that, by default, Prettier looks to enforce formatting standards for all files within the project. In order to ensure that files are not checked, one can create a file `.prettierignore`:

```
.yarn/
vendor/
```

This is a common set of file system patterns which ensure that files within the `.yarn` and `vendor` directories are explicitly ignored by Prettier.

### Checking for Prettier Formatting Violations

The following checks for any violations of the Prettier formatting rules:

```bash
yarn run prettier . --check
```

#### Automatically Correcting Violations

One can also attempt to fix any violations found by Prettier with the following:

```bash
yarn run prettier . --write
```

## Linting JavaScript with [ESLint](https://eslint.org/)

ESLint is a tool used for enforcing specific code formatting standards for JavaScript and TypeScript.

For integrating ESLint into any given project, both Node.js and Yarn are required (as was the case with Prettier).

### Installing ESLint

The following will ensure that ESLint is installed and that the default configuration options used by AirBNB will be applied to the project:
```bash
yarn add -D eslint eslint-plugin-import eslint-config-airbnb-base eslint-config-prettier
```

### Configuring ESLint

ESLint configuration options are set within a file `eslintrc.config.mjs`, which is located at the root path of the project.

The following configuration inherits the default options from `airbnb-base` and ensures that there are no conflicts between ESLint and Prettier:

```js
import globals from 'globals';
import path from 'node:path';
import { fileURLToPath } from 'node:url';
import js from '@eslint/js';
import { FlatCompat } from '@eslint/eslintrc';

const __filename = fileURLToPath(import.meta.url);
const __dirname = path.dirname(__filename);
const compat = new FlatCompat({
  baseDirectory: __dirname,
  recommendedConfig: js.configs.recommended,
  allConfig: js.configs.all,
});

export default [
  ...compat.extends('airbnb-base', 'prettier'),
  {
    languageOptions: {
      globals: {
        ...globals.browser,
      },

      ecmaVersion: 'latest',
      sourceType: 'module',
    },
  },
];
```

Please know that the documentation for the ESLint configuration options are also [publicly available](https://eslint.org/docs/latest/use/configure/).

#### Ignoring Source Code Files

ESLint provides one with the ability to ignore file system patterns within the configuration file with the following:

```js
export default [
  {
    ignores: [".config/*"]
  }
];
```

Please see [the documentation](https://eslint.org/docs/latest/use/configure/ignore) for more details.

### Linting Source Code Files with ESLint

The following lines all source code files using ESLint. By default, the `eslint.config.mjs` file is used for the configuration:

```bash
yarn run eslint
```

#### Automatically Correcting Violations

One can also attempt to fix any linting violations found by ESLint by invoking the following:

```bash
yarn run eslint --fix
```

## Adding ESLint and Prettier to CircleCI

Within the CircleCI configuration file, one can add the following:

```yaml
- run:
    name: Lint using ESLint
    command: yarn run eslint .
- run:
    name: check formatting using prettier
    command: yarn run prettier --check .
```
