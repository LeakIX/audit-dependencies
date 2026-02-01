# Dependency Security Audits

Security audits of all approved dependencies from our dependency policy.

## Structure

```
audit-dependencies/
├── rust/           # Rust crates (crates.io)
├── javascript/     # npm packages
└── python/         # Python packages (PyPI)
```

Each dependency has its own directory with version-specific audit reports:

```
rust/
└── tokio/
    └── v1.43.0.md    # Audit for version 1.43.0
```

## Audit Methodology

Each audit covers:

1. **Package Identity** - Registry, repository, maintainers, typosquatting check
2. **Vulnerabilities** - CVEs, security advisories, unfixed issues
3. **Supply Chain** - Build reproducibility, binary artifacts, install scripts
4. **Code Quality** - Tests, CI/CD, code review, signed releases
5. **Maintenance** - Last release, commit activity, abandonment risk
6. **License** - SPDX identifier, compatibility, transitive licenses
7. **Dependencies** - Transitive count, high-risk deps, tree depth

## Risk Levels

- **LOW** - Well-maintained, no known vulnerabilities, minimal dependencies
- **MEDIUM** - Minor concerns but acceptable for use
- **HIGH** - Significant concerns, use with caution
- **CRITICAL** - Do not use, immediate action required

## Approved Dependencies

See `~/.claude/rules/dependencies.md` for the full list of approved packages.

## Trusted Vulnerability Sources

We rely on the following authoritative sources for vulnerability information:

### Cross-Platform

| Source | URL | Description |
|--------|-----|-------------|
| NVD | https://nvd.nist.gov/ | NIST National Vulnerability Database |
| CVE | https://cve.mitre.org/ | Common Vulnerabilities and Exposures |
| Snyk | https://security.snyk.io/ | Snyk Vulnerability Database |
| OSS Index | https://ossindex.sonatype.org/ | Sonatype OSS Index |
| GitHub Advisories | https://github.com/advisories | GitHub Security Advisory Database |

### Rust

| Source | URL | Description |
|--------|-----|-------------|
| RustSec | https://rustsec.org/advisories/ | Rust Security Advisory Database |
| crates.io | https://crates.io/ | Official Rust package registry |

### JavaScript/TypeScript

| Source | URL | Description |
|--------|-----|-------------|
| npm Advisories | https://www.npmjs.com/advisories | npm Security Advisories |
| npmjs.com | https://www.npmjs.com/ | Official npm registry |

### Python

| Source | URL | Description |
|--------|-----|-------------|
| PyPI | https://pypi.org/ | Python Package Index |
| Safety DB | https://github.com/pyupio/safety-db | Python Safety Database |

## Contributing

To request a new dependency audit:

1. Open an issue with the package name and language
2. Include the use case and alternatives considered
3. Wait for security review before adding to approved list
