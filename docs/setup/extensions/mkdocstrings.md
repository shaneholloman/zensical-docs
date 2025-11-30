---
icon: lucide/code
---

# mkdocstrings

Zensical provides preliminary support for [mkdocstrings],
which allows rendering documentation from source code.

  [mkdocstrings]: https://mkdocstrings.github.io

## Configuration

Configure mkdocstrings as a plugin:

=== "`zensical.toml`"

    ``` toml
    [project.plugins.mkdocstrings.handlers.python]
    inventories = ["https://docs.python.org/3/objects.inv"]
    paths = ["src"]

    [project.plugins.mkdocstrings.handlers.python.options]
    docstring_style = "google"
    inherited_members = true
    show_source = false
    ```

=== "`mkdocs.yml`"

    ``` yaml
    plugins:
      - mkdocstrings:
          handlers:
            python:
              paths: [src]
              inventories:
                - https://docs.python.org/3/objects.inv
              options:
                docstring_style: google
                inherited_members: true
                show_source: false
    ```

The complete list of options can be found in [mkdocstrings' documentation]
as well as [the Python handler documentation].

  [mkdocstrings' documentation]: https://mkdocstrings.github.io/usage/
  [the Python handler documentation]: https://mkdocstrings.github.io/python/usage/

#### Limitations

Zensical detects the use of the mkdocstrings plugin
and automatically enables mkdocstrings' Python Markdown extension.
The plugin hooks are not executed, so for now the cross-references
and backlink functionalities are not available.
We are working on bringing these features again into Zensical.
