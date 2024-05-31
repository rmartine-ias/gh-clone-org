# gh-clone-org

A github-cli extension script to clone all repositories in an organization, optionally filtering by topic or a search string. If the repository has already been cloned it will attempt to switch to the default branch and pull.

## Installation

```bash
gh extension install matt-bartel/gh-clone-org
```

The script will attempt to use `parallel` if it is available, otherwise it will clone repositories one at a time. To install `parallel` on macOS:

```bash
brew install parallel
```

## Usage

```txt
gh clone-org [-t TOPIC] [-s QUERY] [-p PATH] [-y] ORG
  ORG
    Github organization. Required if the GITHUB_ORG environment variable is not set.
  -y, --yes
    Clone without prompting for confirmation.
  -p, --path PATH
    Clone path. Default: current directory.
  -t, --topic TOPIC
    Clone repositories with this topic
  -S, --shallow
    Clone repositories with --depth 1
  -s --search QUERY
    Clone repositories found by this search string. If this is provided '-t' will be ignored.
    Example: -s "is:public language:go"
    See: https://docs.github.com/en/github/searching-for-information-on-github/searching-on-github/searching-for-repositories
  -n, --dry-run
    Do not actually clone, just show what would be cloned
  -1, --single-threaded
    Clone one repository at a time, instead of in parallel.
  -h, --help
    Display this message.
```
