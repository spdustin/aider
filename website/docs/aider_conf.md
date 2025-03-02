---
parent: Configuration
nav_order: 15
description: How to configure aider with a yaml config file.
---

# YAML config file

Most of aider's options can be set in an `.aider.conf.yml` file,
which can be placed in your home directory or at the root of
your git repo. 

{% include special-keys.md %}

Below is a sample of the file, which you
can also
[download from GitHub](https://github.com/paul-gauthier/aider/blob/main/website/assets/sample.aider.conf.yml).

<!--[[[cog
from aider.args import get_sample_yaml
from pathlib import Path
text=get_sample_yaml()
Path("website/assets/sample.aider.conf.yml").write_text(text)
cog.outl("```")
cog.out(text)
cog.outl("```")
]]]-->
```
##########################################################
# Sample .aider.conf.yaml
# This file lists *all* the valid configuration entries.
# Place in your home dir, or at the root of your git repo.
##########################################################

##########
# options:

## show this help message and exit
#help:

#######
# Main:

## Log the conversation with the LLM to this file (for example, .aider.llm.history)
#llm-history-file:

## Specify the OpenAI API key
#openai-api-key:

## Specify the Anthropic API key
#anthropic-api-key:

## Specify the model to use for the main chat (default: gpt-4o)
#model: gpt-4o

## Use claude-3-opus-20240229 model for the main chat
#opus: false

## Use claude-3-5-sonnet-20240620 model for the main chat
#sonnet: false

## Use gpt-4-0613 model for the main chat
#4: false

## Use gpt-4o model for the main chat
#4o: false

## Use gpt-4-1106-preview model for the main chat
#4-turbo: false

## Use gpt-3.5-turbo model for the main chat
#35turbo: false

#################
# Model Settings:

## List known models which match the (partial) MODEL name
#models:

## Specify the api base url
#openai-api-base:

## Specify the api_type
#openai-api-type:

## Specify the api_version
#openai-api-version:

## Specify the deployment_id
#openai-api-deployment-id:

## Specify the OpenAI organization ID
#openai-organization-id:

## Verify the SSL cert when connecting to models (default: True)
#verify-ssl: true

## Specify a file with context window and costs for unknown models
#model-metadata-file:

## Specify what edit format the LLM should use (default depends on model)
#edit-format:

## Specify the model to use for commit messages and chat history summarization (default depends on --model)
#weak-model:

## Only work with models that have meta-data available (default: True)
#show-model-warnings: true

## Max number of tokens to use for repo map, use 0 to disable (default: 1024)
#map-tokens: true

## Maximum number of tokens to use for chat history. If not specified, uses the model's max_chat_history_tokens.
#max-chat-history-tokens:

## Specify the .env file to load (default: .env in git root)
#env-file: .env

################
# History Files:

## Specify the chat input history file (default: .aider.input.history)
#input-history-file: .aider.input.history

## Specify the chat history file (default: .aider.chat.history.md)
#chat-history-file: .aider.chat.history.md

## Restore the previous chat history messages (default: False)
#restore-chat-history: false

##################
# Output Settings:

## Use colors suitable for a dark terminal background (default: False)
#dark-mode: false

## Use colors suitable for a light terminal background (default: False)
#light-mode: false

## Enable/disable pretty, colorized output (default: True)
#pretty: true

## Enable/disable streaming responses (default: True)
#stream: true

## Set the color for user input (default: #00cc00)
#user-input-color: #00cc00

## Set the color for tool output (default: None)
#tool-output-color:

## Set the color for tool error messages (default: red)
#tool-error-color: #FF2222

## Set the color for assistant output (default: #0088ff)
#assistant-output-color: #0088ff

## Set the markdown code theme (default: default, other options include monokai, solarized-dark, solarized-light)
#code-theme: default

## Show diffs when committing changes (default: False)
#show-diffs: false

###############
# Git Settings:

## Enable/disable looking for a git repo (default: True)
#git: true

## Enable/disable adding .aider* to .gitignore (default: True)
#gitignore: true

## Specify the aider ignore file (default: .aiderignore in git root)
#aiderignore: .aiderignore

## Enable/disable auto commit of LLM changes (default: True)
#auto-commits: true

## Enable/disable commits when repo is found dirty (default: True)
#dirty-commits: true

## Perform a dry run without modifying files (default: False)
#dry-run: false

########################
# Fixing and committing:

## Commit all pending changes with a suitable commit message, then exit
#commit: false

## Lint and fix provided files, or dirty files if none provided
#lint: false

## Specify lint commands to run for different languages, eg: "python: flake8 --select=..." (can be used multiple times)
#lint-cmd:

## Enable/disable automatic linting after changes (default: True)
#auto-lint: true

## Specify command to run tests
#test-cmd:

## Enable/disable automatic testing after changes (default: False)
#auto-test: false

## Run tests and fix problems found
#test: false

#################
# Other Settings:

## Use VI editing mode in the terminal (default: False)
#vim: false

## Specify the language for voice using ISO 639-1 code (default: auto)
#voice-language: en

## Show the version number and exit
#version:

## Check for updates and return status in the exit code
#check-update: false

## Skips checking for the update when the program runs
#skip-check-update: false

## Apply the changes from the given file instead of running the chat (debug)
#apply:

## Always say yes to every confirmation
#yes: false

## Enable verbose output
#verbose: false

## Print the repo map and exit (debug)
#show-repo-map: false

## Print the system prompts and exit (debug)
#show-prompts: false

## Specify a single message to send the LLM, process reply then exit (disables chat mode)
#message:

## Specify a file containing the message to send the LLM, process reply, then exit (disables chat mode)
#message-file:

## Specify the encoding for input and output (default: utf-8)
#encoding: utf-8

## Specify the config file (default: search for .aider.conf.yml in git root, cwd or home directory)
#config:

## Run aider in your browser
#gui: false
```
<!--[[[end]]]-->
