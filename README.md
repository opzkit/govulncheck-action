# Govulncheck Action
Run go's vulnerability checker.

- [Vulnerability Management for Go](https://go.dev/blog/vuln)
- [govulncheck docs](https://pkg.go.dev/golang.org/x/vuln/cmd/govulncheck)

# Usage
See [action.yml](action.yml)

## Basic

```yaml
name: Go vulnerabilities check
on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - name: check for go vulnerabilities
      uses: opzkit/govulncheck-action@v1.0.0
      # optional
      with:
        go-version: '1.19'
        govuln-version: 'latest'
        packages: './...'
```

### Inputs

| Input                         | Description                                    |
|-------------------------------|------------------------------------------------|
| `package` _(optional)_        | The package you want to scan, default: "./..." |
| `go-version` _(optional)_     | The go version to use, default: "1.19"         |
| `govuln-version` _(optional)_ | The   govuln version to use, default: "latest" |
