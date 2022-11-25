# Jira Release Create
Create new release

> ##### Only supports Jira Cloud. Does not support Jira Server (hosted)

## Usage

> ##### Note: this action requires [Jira Login Action](https://github.com/marketplace/actions/jira-login)

```yaml
- name: Create Release
  id: create
  uses: martinsbalodis/gajira-create-release@master
  with:
    project: GA
    name: new-release

- name: Log created release
  run: echo "Issue ${{ steps.create.outputs.release }} was created"
```

----
## Action Spec:

### Environment variables
- None

### Inputs
- `project` (required) - Key of the project
- `name` (required) - Release name. Example: 'Product v1.3.5'

### Outputs
- `release` - id of the newly created release

### Reads fields from config file at $HOME/jira/config.yml
- `project`

### Writes fields to config file at $HOME/jira/config.yml
- `release` - a key of a newly created release

### Writes fields to CLI config file at $HOME/.jira.d/config.yml
- `release` - a key of a newly created release