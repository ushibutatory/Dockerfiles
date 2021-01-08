# linear-import

This is unofficial docker image.

- [Official Site](https://linear.app)
- [Import tool](https://github.com/linearapp/linear-import)

## Usage Example

### 1. Prepare import data file

- e.g.) Jira
    1. [Filters] - [Advanced issue search]
    1. Search issues.
    1. [Export] - [Export Excel CSV (all fields)]
    1. Save file.

### 2. Create working Dockerfile

```dockerfile
FROM ushibutatory/linear-import:latest
COPY ./Jira.csv /tmp/Jira.csv
```

work directory structure

```sh
- workdirectory
  - Dockerfile
  - Jira.csv
```

### 3. Run

```bash
> cd workdirectory
> docker build . -t linear-import-test --no-cache
> docker run -it linear-import-test /bin/bash
bash-x# linear-import
? Input your Linear API key (https://linear.app/settings/api) ...
...
Jira (CSV) issues imported to your backlog: ...
```
