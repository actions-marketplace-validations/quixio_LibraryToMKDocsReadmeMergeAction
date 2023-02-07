# Python Container Action Template

Quix Library readme importer.
Import readmes from the Quix Library into MKdocs.

## Usage

Use to add readme.md files from Quix Library to MKDocs

### Example workflow

```yaml
    - name: Quix Library readme importer
      uses: SteveRosam/QuixReadmeAction@Master
      with:
        LIBRARY_REPO_PATH: "library"
        DOCS_PATH: ""
        REPLACEMENT_PLACEHOLDER: "#ConnectorsGetInsertedHere"
        README_DEST: "docs/library_readmes/connectors"
```

### Inputs
LIBRARY_REPO_PATH: Path to where the library is cloned to. e.g. 'library'
DOCS_PATH: Path to where docs is cloned to. Likley leave blank.
REPLACEMENT_PLACEHOLDER: The placeholder that will be replaced with the newly generated nav e.g. "#ConnectorsGetInsertedHere"
README_DEST: Where (in the docs structure) the readme files will be copied to e.g. "docs/library_readmes/connectors"

### Outputs
Outputs an array of strings to the `GITHUB_OUTPUT` environment variable.

Use this code to log the output in your github action yaml file:
```py
- name: Output Importer Logs
  run: |
	for i in ${{ steps.readme_importer.outputs.logs }}; do
	echo $i
	done
```

