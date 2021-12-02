# Get Tag Github Action

Github action built to extract the tag name from the push action.

## Usage

Should be used only when actual tag is pushed, otherwise the Action will exit with an error.

```yaml
on:
  push:
    tags:
      - '*'
```

```yaml
- name: Extract Tag
  id: tag
  uses: aaronbarnaby/get-tag@v1.0.0
  with:
    without_prefix_v: true # Remove prefix `v` from tag

- name: Use Tag
  run: echo ${{ steps.tag.outputs.tag }}
```
