# personal-doc

## Dev

### Set up

Create python virtual environment

```bash
python3 -m venv .venv
```

Load virtual environment

```bash
source .venv/bin/activate
```

Install mkdocs

```bash
pip install -r requirements.txt
```

### Generate requirements.txt

If a new package is added run

```bash
pip freeze > requirements.txt
```

### Run

```bash
mkdocs serve --open --livereload
```

## Deploy on GitHub pages

To publish it manually

```bash
mkdocs gh-deploy
```

Then it should be available on [Personal doc GitHub Pages](https://Yanis-Kouidri.github.io/personal-doc/)
