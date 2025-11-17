# actions_python_fawltydeps
A Github action for python dependency checking with FawltyDeps.

<br/>

## How to use
In your .github/workflows directory, create a yaml file (such as main.yaml). Add a job for each desired workflow with the `uses` keyword. Use the `with` keyword to pass any desired variables.

Examples:

```
on: [push]

jobs:
  fawltydeps:
    runs-on: ubuntu-latest
    name: "fawltydeps"
    steps:
      - uses: davidslusser/actions_python_fawltydeps@v1.0.0
```

<br/>

```
on: [push]

jobs:
  fawltydeps:
    runs-on: ubuntu-latest
    name: "fawltydeps"
    steps:
      - uses: davidslusser/actions_python_fawltydeps@v1.0.0
        with:
          options: "--check-undeclared --check-unused"
          pip_install_command: "pip install -e .[dev] && pip install fawltydeps"
          python_version: "3.13"
```


<br/>

## Inputs
  - **options:** optional flags/parameters used in fawltydeps command (defaults to "")
  - **pip_install_command:** pip install command (defaults to "pip install fawltydeps")
  - **python_version:** version of python to run workflow with (defaults to "3.x")
  - **command:** command to run fawltydeps; overrides default command and options (defaults to "")


<br/>

## References
 - https://github.com/tweag/FawltyDeps
 - https://pypi.org/project/fawltydeps/
