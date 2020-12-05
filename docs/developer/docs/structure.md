# Document Structure

## Menu

The relationship between menu and page is defined in `mkdocs.yaml`.

```yaml
nav:
  - Home: // Top level menu.
  - Application: // Documents about application.
      - Get Started: app/get-started.md
      - Name of Page: Relative path under docs.
  - Campus: // Documents about campus.
  - Developer: // Documents for developers.
```

## Format

The format of markdown that used in documents is extended by serveral plugins to present more acceptable document. Visit [documents of extensions](https://squidfunk.github.io/mkdocs-material/reference/admonitions/) for more information.