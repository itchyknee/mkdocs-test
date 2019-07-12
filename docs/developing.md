# Developing

## Source control

We follow [GDS guidance on maintaining version controlled code](https://www.gov.uk/service-manual/technology/maintaining-version-control-in-coding).

We use [Git](https://git-scm.com/) and [Gitlab](https://gitlab.com/nhsbsa) for production code.
We are migrating our legacy codebase from [Subversion](https://subversion.apache.org/).

## Development environment

We are agnostic on tool choices, but they must be configured to work well as a team (such as using agreed code styles). The most popular IDEs in use are Eclipse and IntelliJ. If you choose to use Eclipse, there is a pre-built version of Eclipse for Windows.

### Builds

We use [Maven](https://maven.apache.org/) as our build tool.

## Documentation

We document our code with a README at the top level of the code repository.

We follow 'Clean Code' rules for comments:

1. Always try to explain yourself in code.
1. Don't be redundant.
1. Don't add obvious noise. This includes 'bugfix #' comments
1. Don't use closing brace comments.
1. Don't comment out code. Just remove.
1. Use as explanation of intent.
1. Use as clarification of code.
1. Use as warning of consequences.

## Technology choice

TODO

## Clean code

We encourage that every developer reads [Clean Code: A Handbook of Agile Software Craftsmanship](https://www.amazon.co.uk/dp/0132350882). by Robert Martin (a.k.a. Uncle Bob).

### Test Driven Development

We strongly encourage Test Driven Development, but it is not enforced. Try it, you might like it.

### Technical debt

We sometimes have to get things out of the door when we're not completely happy with the way it's working. When this happens we record it as _technical debt_. We will try to fix debt in the next sprint.

### Bugs

When we get things wrong, defects are raised in Jira. We always try to fix them within the sprint.
We try very hard to avoid a backlog of bugs: fix them or accept them as low-priority, won't fix.

### Refactoring

We try to follow the scouting rule of leaving the campsite in a better state than when we found it.
To do this we encourage [refactoring](https://refactoring.guru/refactoring).

### Style guide

We use the [Google style guides](http://google.github.io/styleguide/).

## Continuous Integration

We perform Continuous Integration builds on every push to a _feature_ branch.

A CI build will:

* Compile
* Unit Test (Maven Surefire)
* Integration Test (Maven Failsafe)
* Enforce automated code quality rules

We use Gitlab-CI for our build pipeline. This allows us to run downstream dependencies such as a database in a Docker container.

### Automated code quality checks

We use SonarQube to enforce code quality according to static analysis and code test coverage quality gate.

### Code reviews

We require that all code changes are merged into _master_ by a different developer to the one(s) that made the changes.
Gitlab provides a great interface for feedback.
