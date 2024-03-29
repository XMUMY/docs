# Contribute to Documents

XMUX Help Center is powered by [mkdocs](https://www.mkdocs.org/) with its themes and plugins.

## Prerequisite

- Markdown
- [Github](https://github.com) Account
- Basic operations of Git repository.
- Installation of Python 3 and Python packages.

!!! note

    The last prerequisite is required only when you want to set up a local environment.

## Local Environment Setup

1. Install [Python 3](https://www.python.org/).
2. Install following Python packages.

    - mkdocs
    - mkdocs-material
    - pygments

    Which usually can be done by `pip3 install mkdocs mkdocs-material pygments` or `conda install -c conda-forge mkdocs mkdocs-material` if you are using conda.

3. Clone repository of documents.

    ```bash
    git clone https://github.com/XMUMY/docs
    ```

4. Start a local server.

    ```bash
    cd docs
    mkdocs serve
    ```

    The document website should be able for visiting through [http://127.0.0.1:8000](http://127.0.0.1:8000)
