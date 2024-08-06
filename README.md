
<h1 align="center">Github Workflows</h1>

> Reusable GitHub Workflows to be used in other repositories



## Example

```yaml

  create_release_example:
    uses: "platomo/GitHub-workflows/.github/workflows/reusable-create-release-with-assets.yml@main"
    secrets:
      PLATOMO_BUILDER_ACCESS: ${{ secrets.PLATOMO_BUILDER_ACCESS }}
    with:
      package-path: OTVision
      package-version: ${{ github.ref_name }}
      draft-release: false
      pre-release: false
      delete-existing: false
      
      
  run_tests_example:
    strategy:
      fail-fast: True
      matrix:
        os: [ubuntu-latest, windows-latest]
        py: ["3.11"]
    uses: 'platomo/GitHub-workflows/.github/workflows/reusable-python-tests.yml@main'
    with:
      os: ${{ matrix.os }}
      py-version: ${{ matrix.py }}
      test_path: OTAnalytics
    
```

