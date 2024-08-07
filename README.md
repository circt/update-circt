# Update CIRCT

Composite GitHub action to update [`llvm/circt`](https://github.com/llvm/circt)
binaries/libraries in a downstream project.

# Usage

```yaml
- name: Update CIRCT
  uses: circt/update-circt@v1
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

    # An optional script to decide whether to open the Pull Request or not.
    # The script must accept a single positional argument (the new CIRCT
    # version). The script is only run when there is a new version of CIRCT.  A
    # return value of 0 means "open the PR". A return value of 1 means "do not
    # open the PR". Any other return value will cause the action to exit with
    # an error. Note, the default value 'true' is the shell built-in, not a
    # boolean value.
    #
    # Default: 'true'
    should-create-pr: ''

    # A GitHub token with sufficient permissions to create Pull Requests
    #
    # Default: ${{ github.token }}
    github-token: ''
```
