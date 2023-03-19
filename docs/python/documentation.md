# Writing Documentation

> Friends don't let friends write undocumented code.

Use mkdocs. It powers this "documentation".

Setting it up is simple enough :

<div class="termy">

```console
$ mkdocs serve
color:green Serving on http://127.0.0.1:8000/
```

</div>

## Installation

User the following packages:

| Library               | Description                                                                      |
| --------------------- | -------------------------------------------------------------------------------- |
| `mkdocs`              | The documentation engine.                                                        |
| `mkdocs-material`     | Probably the best documentation theme.                                           |
| `mkdocs-bibtex`       | Adds BibTeX support to your docs.                                                |
| `mkdocs-gen-files`    | Can generate arbitrary files on the fly. Useful for automatic API documentation. |
| `mkdocstrings`        | Generate API documentation. Use it with `mkdocs-gen-files`.                      |
| `mkdocstrings-python` | A Python API docs rendering engine.                                              |
| `mkdocs-glightbox`    | Better image handling. Plays well with the material theme.                       |

Then create a `docs` folder as well as a `mkdocs.yml` configuration file at the root of your project.

You can take this project's [configuration](https://github.com/bdura/project-template/blob/main/mkdocs.yml) as reference.

## Recipes

### Using BibTeX

See the [bibtex file](https://github.com/bdura/project-template/blob/main/docs/references.bib) and the [index](https://github.com/bdura/project-template/blob/main/docs/index.md?plain=1) for an example. See also the [dedicated configuration](https://github.com/bdura/project-template/blob/main/mkdocs.yml#L64).

Another example : water consumption in France[@conso-eau].

### Using notebooks

Use the [`mkdocs-jupyter` library](https://github.com/danielfrg/mkdocs-jupyter). See the [example](../examples/using-jupyter.ipynb).

!!! note "Adding the jupyter notebook to Git"

    It's good practice to Git-ignore notebooks (`*.ipynb` files).

    You can still force Git to add an ignored file using the command `git add --force normally-ignored-file.ipynb`.
