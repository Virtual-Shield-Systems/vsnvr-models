# vsnvr-models

Hash-pinned model files for VS-NVR's AI-detection sidecar, published as release assets.
The integrity manifest (`deploy/aidetect/models/manifest.json`) and the fetch tool
(`scripts/fetch-model.py`) live in the VS-NVR repository. Each asset name carries the
first 8 hex digits of its sha256, so a published name never changes content.

Every model here was published by its authors under the Apache License 2.0
([LICENSE](LICENSE)) and is redistributed under it. Virtual Shield Systems converted
some of them to ONNX; [NOTICE](NOTICE) records each file's upstream source, revision,
changes and training data.

| Asset (release `aidetect-models-v1`) | Model | Upstream | Changes | Training data |
|---|---|---|---|---|
| `rtdetr-v2-r18-coco-6436e6ac.onnx` | RT-DETRv2-S object detector | [`PekingU/rtdetr_v2_r18vd`](https://huggingface.co/PekingU/rtdetr_v2_r18vd) @ `5650961` | Exported to ONNX, outputs merged | COCO 2017 only; ImageNet-1k backbone |
| `plate-rtdetr-v2-r18-50f9bf9d.onnx` | RT-DETRv2-R18 plate detector | [`Topurrra/rtdetr-license-plate-detection-onnx`](https://huggingface.co/Topurrra/rtdetr-license-plate-detection-onnx) @ `aecb24a` | None | Open Images V7 plates, from the COCO model above |
| `siglip2-b16-224-*` (5 files) | SigLIP 2 image/text embeddings | [`google/siglip2-base-patch16-224`](https://huggingface.co/google/siglip2-base-patch16-224) @ `75de2d5` | Exported to ONNX, text table int8 | WebLI (not public) |
| `rtdetr-r18-o365-a8b2b37f.onnx` | RT-DETR-R18, superseded | [`PekingU/rtdetr_r18vd_coco_o365`](https://huggingface.co/PekingU/rtdetr_r18vd_coco_o365) @ `386c438` | Exported to ONNX, outputs merged | Objects365 (academic use only) + COCO |

The last file is no longer used by VS-NVR. It stays only so older source revisions,
which pin it by hash, still build. Its Objects365 pretraining means it should not be
assumed to be cleared for commercial use.

The models are provided "as is", without warranties of any kind; see the License.
