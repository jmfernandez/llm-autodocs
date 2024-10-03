# llm-autodocs 🪄

**DISCLAIMER**: This repo is a fork of https://github.com/jerpint/llm-autodocs , created to add local ollama servers usage capabilities.

## Overview 🌞

`autodocs` is a Python-based command-line tool for automatically generating documentation for git-tracked Python files in a project. It leverages LLMs to generate documentation automatically and asynchronously.

## Features ⚡️
* Git Integration: Only selects Python files that are tracked by Git within a specified directory.
* Custom File Selection: Offers the flexibility to specify files to include or exclude in the documentation process.
* LLM Support: Currently supports both OpenAI gpt models and ollama local server ones.
* Asynchronous Execution: Improves performance by handling multiple files concurrently.

## Quickstart 🚴‍♂️

Install the library:

```bash
pip install git+https://github.com/jmfernandez/llm-autodocs
```

Navigave to your git project and run:

```bash
cd my_project/
autodocs --directory .
```

If you want to use your local ollama server with your selected model, it would be:

```bash
cd my_project/
autodocs --local-server http://localhost:11434 --documenter mistral:latest --directory .
```


Any of these alternatives will run in the root of your project and include all tracked .py files. By default it uses `gpt-3.5-turbo`.

You will be prompted to review the files affected before continuing.

## Examples

Specify a specific directory:

    autodocs --directory ./src

Specify a different openai model (can be any of the gpt-3.5* or gpt-4* patterns):

    autodocs --documenter gpt-4

Allow only certain file patterns:

    autodocs --allowed-files utils.py data_model.py

Exclude certain file patterns:

    autodocs --ignored-files __init__.py
