# palaver-models

Pre-chunked ONNX model weights for [Palaver](https://github.com/Sm0keSkreen/Palaver),
split into <20MB files for jsDelivr's per-file size limit.

| Model | Folder | Size |
|---|---|---|
| Gemma 270M | `gemma270m/` | ~320MB |
| Gemma 1B | `gemma1b/` | ~860MB |
| Gemma 4 E2B | `gemma4e2b/` | ~3.4GB |

## How chunking works

ONNX model weights are split into shards under 20MB each. At runtime,
[transformers.js](https://huggingface.co/docs/transformers.js) reassembles
them via a custom Cache-API shim that merges chunks on first load, then serves
the assembled file directly on subsequent loads.

Weights load from this repo's CDN folder by default. If the CDN is unreachable,
[Palaver](https://github.com/Sm0keSkreen/Palaver) falls back to fetching
directly from the original Hugging Face repos.
