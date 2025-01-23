## What is pyscan?

<center><img src="https://i.imgur.com/wxD7uTN.png" height="auto" width="auto"></center>


Pyscan is a CLI tool that finds dependencies in your Python project and reports any security vulnerability found. This action integrates it to your CI to automatically find vulns and reporting them.

- It uses [osv.dev](https://osv.dev/) as its advisory (its open source and free).
- Pyscan can find dependencies from requirements, pyproject, setup.py and even straight from the source code. supports poetry, filt, hatch, pdm, etc
- Supports formatted text output and json.

## Add it to your repo

Here's a setup file to scan for vulnerabilities on push, modify it to your needs.

Create `.github/workflows/pyscan.yml`

Paste this in there:
```yaml
name: Pyscan dependency scan

on: push
jobs:
  security:
    runs-on: ubuntu-latest
    steps:
      - name: Pyscan 
        uses: aswinnnnn/pyscan@1.0.0
```

## Options

| Option              | Description | Required | Default |
| --------             | ------- | -------- | ------- | 
| `path`               |Directory to scan for vulnerabilities, defaults to current (incase the requirements.txt, pyproject.toml,etc is in a deeper path)         |  false  | .        |
| `output-format`      |Output format for scan results uploaded as artifact (currently only json)         | false         |   json      |
| `upload-artifact`    | Whether to upload scan results as an artifact |  false       |     false  |
| `artifact-name`      | Name of the uploaded artifact (without the extension)        |      false    |    `pyscan-results`     |

`output-format` only applies to the saved output file, pyscan will display readable and pretty good text and summary in the logs/console

## Notes

Please let me know about improvements/issues and open pull requests if you have the time to implement them yourself.

## Donate

I maintain pyscan and pyscan-check all by myself while in college while being broke. Any kind of help matters.

<h3 align="center"><a href="https://ko-fi.com/aswinnnn"> <img align="center" src="https://cdn.ko-fi.com/cdn/kofi3.png?v=3" height="50" width="210" alt="goldenboi" /></a></h3>


