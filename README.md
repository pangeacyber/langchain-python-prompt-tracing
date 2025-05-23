# Prompt Tracing for LangChain in Python

An example Python app demonstrating how to integrate Pangea's [Secure Audit Log][]
service into a LangChain app to maintain an audit log of prompts being sent to
LLMs.

## Prerequisites

- Python v3.12 or greater.
- pip v24.2 or [uv][] v0.4.29.
- A [Pangea account][Pangea signup] with Secure Audit Log enabled with the
  AI Audit Log Schema Config.
- An [OpenAI API key][OpenAI API keys].

## Setup

```shell
git clone https://github.com/pangeacyber/langchain-python-prompt-tracing.git
cd langchain-python-prompt-tracing
```

If using pip:

```shell
python -m venv .venv
source .venv/bin/activate
pip install .
```

Or, if using uv:

```shell
uv sync
source .venv/bin/activate
```

The sample can then be executed with:

```shell
python -m langchain_prompt_tracing "Give me information on John Smith"
```

## Usage

```
Usage: python -m langchain_prompt_tracing [OPTIONS] PROMPT

Options:
  --model TEXT             OpenAI model.  [default: gpt-4o-mini; required]
  --audit-token SECRET     Pangea Secure Audit Log API token. May also be set
                           via the `PANGEA_AUDIT_TOKEN` environment variable.
                           [required]
  --audit-config-id TEXT   Pangea Secure Audit Log configuration ID.
  --pangea-domain TEXT     Pangea API domain. May also be set via the
                           `PANGEA_DOMAIN` environment variable.  [default:
                           aws.us.pangea.cloud; required]
  --openai-api-key SECRET  OpenAI API key. May also be set via the
                           `OPENAI_API_KEY` environment variable.  [required]
  --help                   Show this message and exit.
```

### Example Input/Output

This does not modify the input or output so it's transparent to the LLM and end
user.

Audit logs can be viewed at the [Secure Audit Log Viewer][].

[Secure Audit Log]: https://pangea.cloud/docs/audit/
[Secure Audit Log Viewer]: https://console.pangea.cloud/service/audit/logs
[Pangea signup]: https://pangea.cloud/signup
[OpenAI API keys]: https://platform.openai.com/api-keys
[uv]: https://docs.astral.sh/uv/
