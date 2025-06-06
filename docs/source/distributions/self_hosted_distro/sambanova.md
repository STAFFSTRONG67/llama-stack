---
orphan: true
---
<!-- This file was auto-generated by distro_codegen.py, please edit source -->
# SambaNova Distribution

```{toctree}
:maxdepth: 2
:hidden:

self
```

The `llamastack/distribution-sambanova` distribution consists of the following provider configurations.

| API | Provider(s) |
|-----|-------------|
| agents | `inline::meta-reference` |
| inference | `remote::sambanova` |
| safety | `inline::llama-guard` |
| telemetry | `inline::meta-reference` |
| tool_runtime | `remote::brave-search`, `remote::tavily-search`, `inline::code-interpreter`, `inline::rag-runtime` |
| vector_io | `inline::faiss`, `remote::chromadb`, `remote::pgvector` |


### Environment Variables

The following environment variables can be configured:

- `LLAMASTACK_PORT`: Port for the Llama Stack distribution server (default: `8321`)
- `SAMBANOVA_API_KEY`: SambaNova.AI API Key (default: ``)

### Models

The following models are available by default:

- `Meta-Llama-3.1-8B-Instruct (aliases: meta-llama/Llama-3.1-8B-Instruct)`
- `Meta-Llama-3.1-70B-Instruct (aliases: meta-llama/Llama-3.1-70B-Instruct)`
- `Meta-Llama-3.1-405B-Instruct (aliases: meta-llama/Llama-3.1-405B-Instruct-FP8)`
- `Meta-Llama-3.2-1B-Instruct (aliases: meta-llama/Llama-3.2-1B-Instruct)`
- `Meta-Llama-3.2-3B-Instruct (aliases: meta-llama/Llama-3.2-3B-Instruct)`
- `Meta-Llama-3.3-70B-Instruct (aliases: meta-llama/Llama-3.3-70B-Instruct)`
- `Llama-3.2-11B-Vision-Instruct (aliases: meta-llama/Llama-3.2-11B-Vision-Instruct)`
- `Llama-3.2-90B-Vision-Instruct (aliases: meta-llama/Llama-3.2-90B-Vision-Instruct)`
- `Meta-Llama-Guard-3-8B (aliases: meta-llama/Llama-Guard-3-8B)`
- `Llama-4-Scout-17B-16E-Instruct (aliases: meta-llama/Llama-4-Scout-17B-16E-Instruct)`


### Prerequisite: API Keys

Make sure you have access to a SambaNova API Key. You can get one by visiting [SambaNova.ai](https://sambanova.ai/).


## Running Llama Stack with SambaNova

You can do this via Conda (build code) or Docker which has a pre-built image.

### Via Docker

This method allows you to get started quickly without having to build the distribution code.

```bash
LLAMA_STACK_PORT=8321
docker run \
  -it \
  --pull always \
  -p $LLAMA_STACK_PORT:$LLAMA_STACK_PORT \
  llamastack/distribution-sambanova \
  --port $LLAMA_STACK_PORT \
  --env SAMBANOVA_API_KEY=$SAMBANOVA_API_KEY
```

### Via Conda

```bash
llama stack build --template sambanova --image-type conda
llama stack run ./run.yaml \
  --port $LLAMA_STACK_PORT \
  --env SAMBANOVA_API_KEY=$SAMBANOVA_API_KEY
```
