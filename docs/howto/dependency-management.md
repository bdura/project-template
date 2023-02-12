# Dependency Management with Poetry

Poetry is a strict dependency management tool that makes sure your Python environment
is fully reproducible.

To that end, Poetry keeps track of all dependencies (meaning the requirements you specify,
as well as their requirements, recursively) and saves the state of your environment into
a `poetry.lock` file.

!!! note "This is standard practice"

    For instance, in JavaScript, the packager Yarn keeps a `yarn.lock` file for the exact same purpose.

Poetry is configured within a `pyproject.toml` file, where (potentially lax) constraints are
placed on your requirements. When you install for the first time, Poetry will:

- Make sure the constraints can be resolved (eg you specify `pandas>1.2` and
  `some-library`, which specifies `pandas<1.1.4` internally)
- Install the most up-to-date relevant version for every dependency.

Then, you can update your environment with `poetry update`. Poetry will again
install the most up-to-date relevant version for every dependency.

See Poetry's refresher course on semantic versionning if need be.

## Installing a new dependency

Poetry introduces the concept of *dependency group*. Your project may require a library to run,
or for development purposes (eg formatter, linter, tests).

It's best practice to divide theses into groups. Let's say your project needs Pandas to run,
and Pytest for testing. One way to install those would be:

<div class="termy">

```console
color:grey # Add pandas to the default group
$ poetry add pandas
---> 100%
color:grey # Add pytest to the "test" group
$ poetry add --group test pytest
---> 100%
```

</div>

## Removing a dependency

Call `poetry remove [--group]` to remove a dependency.

<div class="termy">

```console
$ poetry remove pandas
---> 100%
```

</div>
