---
license: gemma
base_model:
- google/gemma-4-E2B-it
library_name: transformers.js
tags:
- gemma4
- gemma
- google
- multimodal
pipeline_tag: text-generation
---

# Gemma 4 E2B

Chunked q4f16 ONNX weights for [Gemma 4 E2B](https://huggingface.co/onnx-community/gemma-4-E2B-it-ONNX),
served via jsDelivr CDN for Palaver.

This is Gemma 4's smallest tier — a multimodal any-to-any model (text + vision + audio)
with ~2B effective parameters. Despite the small param count, the download is ~3.2GB
because every Gemma 4 variant includes vision and audio encoder weights.

## Files included

Only the `q4f16` quantization variant is shipped (matching Palaver's dtype setting):

- `onnx/decoder_model_merged_q4f16.onnx` + chunked `_data`
- `onnx/embed_tokens_q4f16.onnx` + chunked `_data`
- `onnx/vision_encoder_q4f16.onnx` + chunked `_data`
- `onnx/audio_encoder_q4f16.onnx` + chunked `_data`
- Tokenizer, config, and processor files
