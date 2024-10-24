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
# @class My Class Desc
# @author Alice Smith
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
