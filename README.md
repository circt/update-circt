# Update CIRCT

Composite GitHub action to update [`llvm/circt`](https://github.com/llvm/circt)
binaries/libraries in a downstream project.

# Usage

```yaml
- name: Update CIRCT
  uses: circt/update-circt@v1.0.0
  with:
    # The name that will be associated with any created commits
    user: ''

    # The email address that will be associated with any created commits
    email: ''

    # A comma or newline separate list of reviewers for the created Pull
    # Request
    pr-reviewers: ''

    # A comma or newline separated list of labels to apply to the created
    # Pull Request
    pr-labels: ''

    # The name of the branch containing accumulated patches that need to be
    # applied in order for the latest CIRCT to work with Chisel.
    #
    # Default: 'ci/ci-circt-nightly'
    staging-branch: ''

    # The location, within the downstream project repository, of the
    # configuration file which sets the CIRCT version.  This workflow assumes
    # that this is a JSON object containing a key "version".
    #
    # Default: './etc/circt.json'
    circt-config: ''

    # A GitHub token with sufficient permissions to create Pull Requests
    #
    # Default: ${{ github.token }}
    github-token: ''
```
