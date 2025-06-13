# Govulncheck Action

Run go's vulnerability checker.

- [Vulnerability Management for Go](https://go.dev/blog/vuln)
- [govulncheck docs](https://pkg.go.dev/golang.org/x/vuln/cmd/govulncheck)

# Usage

See [action.yml](action.yml)

## Basic

<!-- x-release-please-start-version -->
```yaml
name: Go vulnerabilities check
on: [ push ]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: check for go vulnerabilities
        uses: opzkit/govulncheck-action@v1.1.1
        # optional
        with:
          go-version: '1.19'
          govuln-version: 'latest'
          packages: './...'
```
<!-- x-release-please-end-->

### Inputs

| Input                          | Description                                                                                     |
|--------------------------------|-------------------------------------------------------------------------------------------------|
| `package` _(optional)_         | The package you want to scan, default: "./..."                                                  |
| `go-version` _(optional)_      | The go version to use, default: "1.19"                                                          |
| `go-version-file` _(optional)_ | Path to the go.mod file to use for determining go version                                       |
| `check-latest` _(optional)_    | Check for latest available go version that satisfies the version spec, default default: "false" |
| `govuln-version` _(optional)_  | The govuln version to use, default: "latest"                                                    |
