---
parent: Configuration
nav_order: 900
description: Using a .env file to store LLM API keys for aider.
---

# Config with .env

You can use a `.env` file to store API keys and other settings for the
models you use with aider.
You can also set many general aider options
in the `.env` file.

{% include special-keys.md %}

Aider will look for a `.env` file in the
root of your git repo or in the current directory.
You can give it an explicit file to load with the `--env-file <filename>` parameter.

Below is a sample `.env` file, which you
can also
[download from GitHub](https://github.com/paul-gauthier/aider/blob/main/website/assets/sample.env).

<!--[[[cog
from aider.args import get_sample_dotenv
from pathlib import Path
text=get_sample_dotenv()
Path("website/assets/sample.env").write_text(text)
cog.outl("```")
cog.out(text)
cog.outl("```")
]]]-->
```
##########################################################
# Sample aider .env file.
# Place at the root of your git repo.
# Or use `aider --env <fname>` to specify.
##########################################################

#################
# LLM parameters:
#
# Include xxx_API_KEY parameters and other params needed for your LLMs.
# See https://aider.chat/docs/llms.html for details.

## OpenAI
#OPENAI_API_KEY=

## Anthropic
#ANTHROPIC_API_KEY=

##...

#######
# Main:

## Log the conversation with the LLM to this file (for example, .aider.llm.history)
#AIDER_LLM_HISTORY_FILE=

## Specify the OpenAI API key
#OPENAI_API_KEY=

## Specify the Anthropic API key
#ANTHROPIC_API_KEY=

## Specify the model to use for the main chat (default: gpt-4o)
#AIDER_MODEL=gpt-4o

## Use claude-3-opus-20240229 model for the main chat
#AIDER_OPUS=

## Use claude-3-5-sonnet-20240620 model for the main chat
#AIDER_SONNET=

## Use gpt-4-0613 model for the main chat
#AIDER_4=

## Use gpt-4o model for the main chat
#AIDER_4O=

## Use gpt-4-1106-preview model for the main chat
#AIDER_4_TURBO=

## Use gpt-3.5-turbo model for the main chat
#AIDER_35TURBO=

#################
# Model Settings:

## List known models which match the (partial) MODEL name
#AIDER_MODELS=

## Specify the api base url
#OPENAI_API_BASE=

## Specify the api_type
#OPENAI_API_TYPE=

## Specify the api_version
#OPENAI_API_VERSION=

## Specify the deployment_id
#OPENAI_API_DEPLOYMENT_ID=

## Specify the OpenAI organization ID
#OPENAI_ORGANIZATION_ID=

## Verify the SSL cert when connecting to models (default: True)
#AIDER_VERIFY_SSL=true

## Specify a file with context window and costs for unknown models
#AIDER_MODEL_METADATA_FILE=

## Specify what edit format the LLM should use (default depends on model)
#AIDER_EDIT_FORMAT=

## Specify the model to use for commit messages and chat history summarization (default depends on --model)
#AIDER_WEAK_MODEL=

## Only work with models that have meta-data available (default: True)
#AIDER_SHOW_MODEL_WARNINGS=true

## Max number of tokens to use for repo map, use 0 to disable (default: 1024)
#AIDER_MAP_TOKENS=true

## Maximum number of tokens to use for chat history. If not specified, uses the model's max_chat_history_tokens.
#AIDER_MAX_CHAT_HISTORY_TOKENS=

## Specify the .env file to load (default: .env in git root)
#AIDER_ENV_FILE=.env

################
# History Files:

## Specify the chat input history file (default: .aider.input.history)
#AIDER_INPUT_HISTORY_FILE=.aider.input.history

## Specify the chat history file (default: .aider.chat.history.md)
#AIDER_CHAT_HISTORY_FILE=.aider.chat.history.md

## Restore the previous chat history messages (default: False)
#AIDER_RESTORE_CHAT_HISTORY=false

##################
# Output Settings:

## Use colors suitable for a dark terminal background (default: False)
#AIDER_DARK_MODE=false

## Use colors suitable for a light terminal background (default: False)
#AIDER_LIGHT_MODE=false

## Enable/disable pretty, colorized output (default: True)
#AIDER_PRETTY=true

## Enable/disable streaming responses (default: True)
#AIDER_STREAM=true

## Set the color for user input (default: #00cc00)
#AIDER_USER_INPUT_COLOR=#00cc00

## Set the color for tool output (default: None)
#AIDER_TOOL_OUTPUT_COLOR=

## Set the color for tool error messages (default: red)
#AIDER_TOOL_ERROR_COLOR=#FF2222

## Set the color for assistant output (default: #0088ff)
#AIDER_ASSISTANT_OUTPUT_COLOR=#0088ff

## Set the markdown code theme (default: default, other options include monokai, solarized-dark, solarized-light)
#AIDER_CODE_THEME=default

## Show diffs when committing changes (default: False)
#AIDER_SHOW_DIFFS=false

###############
# Git Settings:

## Enable/disable looking for a git repo (default: True)
#AIDER_GIT=true

## Enable/disable adding .aider* to .gitignore (default: True)
#AIDER_GITIGNORE=true

## Specify the aider ignore file (default: .aiderignore in git root)
#AIDER_AIDERIGNORE=.aiderignore

## Enable/disable auto commit of LLM changes (default: True)
#AIDER_AUTO_COMMITS=true

## Enable/disable commits when repo is found dirty (default: True)
#AIDER_DIRTY_COMMITS=true

## Perform a dry run without modifying files (default: False)
#AIDER_DRY_RUN=false

########################
# Fixing and committing:

## Commit all pending changes with a suitable commit message, then exit
#AIDER_COMMIT=false

## Lint and fix provided files, or dirty files if none provided
#AIDER_LINT=false

## Specify lint commands to run for different languages, eg: "python: flake8 --select=..." (can be used multiple times)
#AIDER_LINT_CMD=

## Enable/disable automatic linting after changes (default: True)
#AIDER_AUTO_LINT=true

## Specify command to run tests
#AIDER_TEST_CMD=

## Enable/disable automatic testing after changes (default: False)
#AIDER_AUTO_TEST=false

## Run tests and fix problems found
#AIDER_TEST=false

#################
# Other Settings:

## Use VI editing mode in the terminal (default: False)
#AIDER_VIM=false

## Specify the language for voice using ISO 639-1 code (default: auto)
#AIDER_VOICE_LANGUAGE=en

## Check for updates and return status in the exit code
#AIDER_CHECK_UPDATE=false

## Skips checking for the update when the program runs
#AIDER_SKIP_CHECK_UPDATE=false

## Apply the changes from the given file instead of running the chat (debug)
#AIDER_APPLY=

## Always say yes to every confirmation
#AIDER_YES=

## Enable verbose output
#AIDER_VERBOSE=false

## Print the repo map and exit (debug)
#AIDER_SHOW_REPO_MAP=false

## Print the system prompts and exit (debug)
#AIDER_SHOW_PROMPTS=false

## Specify a single message to send the LLM, process reply then exit (disables chat mode)
#AIDER_MESSAGE=

## Specify a file containing the message to send the LLM, process reply, then exit (disables chat mode)
#AIDER_MESSAGE_FILE=

## Specify the encoding for input and output (default: utf-8)
#AIDER_ENCODING=utf-8

## Run aider in your browser
#AIDER_GUI=false
```
<!--[[[end]]]-->


