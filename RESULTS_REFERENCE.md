# Results: 224 Stable Diffusion XL Inference Baseline

**Main goal:** Measure SDXL image-generation performance  
**Tools:** Run scripts/collect_sdxl.py --backend sdxl with real SDXL in every profile; smoke uses reduced resolution and steps

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_148 · recorded 2026-11-19). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× NVIDIA H100 NVL (95830 MiB) · AMD EPYC 9374F 32-Core Processor · Ubuntu 24.04.5 LTS · kernel 6.8.0-138-generic · driver 595.112.07
- **Run:** 2026-11-19T15:31:06Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 01:32 · benchmark 00:01 · whole run 01:43
- **Source:** run 224_20261119_153106
- **Command:** `bash run_benchmark.sh --smoke --model-name sdxl-base-1.0 --precision fp16 --scheduler euler --prompt-source synthetic --image-resolution 64 --num-images 1 --num-inference-steps 2 --guidance-scale 0 --seed 42 --prompt-len 32 --batch-size 1`

| # | Metric | Result |
|---|---|---|
| 1 | Per-image latency (per_image_latency_sec) | 0.117444 |
| 2 | Aggregate throughput (images_per_sec) | 8.514696365927591 |
| 3 | Peak VRAM, GB (peak_vram_gb) | 8.172601 |
| 4 | Denoising step time per batch, ms (step_time_ms) | 42.103724 |
| 5 | First-image latency, cold (first_image_latency_s) | 4.821306 |
<!-- /profile:smoke -->
