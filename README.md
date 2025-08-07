# CodeIgniter4 Default Templates for GitHub

This repository contains the default templates for GitHub for the CodeIgniter
organization.

### Using Reusable Workflows

Each reusable workflow defines `inputs` under the `workflow_call` trigger.
If you don't specify your own inputs, the workflow will use the defined default values.

To customize inputs, you must define them under the `with` section in your workflow.

**Basic Example:**

```yaml
jobs:
  psalm:
    uses: codeigniter4/.github/.github/workflows/psalm.yml@CI46
    with:
      php-version: '8.2'
```

**Advanced Example (Using Matrix Strategy)**

```yaml
jobs:
  rector:
    strategy:
      fail-fast: false
      matrix:
        php-version: ['8.2', '8.4']

    uses: codeigniter4/.github/.github/workflows/rector.yml@CI46
    with:
      php-version: ${{ matrix.php-version }}
```