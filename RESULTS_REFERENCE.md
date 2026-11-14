# Results: 224 Stable Diffusion XL Inference Baseline

**Main goal:** Measure SDXL image-generation performance  
**Tools:** Run scripts/collect_sdxl.py --backend sdxl with real SDXL in every profile; smoke uses reduced resolution and steps

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_140 · recorded 2026-11-13). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× NVIDIA H100 PCIe (81559 MiB) · Intel(R) Xeon(R) Platinum 8352Y CPU @ 2.20GHz · Ubuntu 24.04.5 LTS · kernel 6.8.0-138-generic · driver 595.91.07
- **Run:** 2026-11-13T21:12:55Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 03:17 · benchmark 00:13 · whole run 03:49
- **Source:** run 224_20261113_211255
- **Command:** `bash run_benchmark.sh --smoke --model-name sdxl-base-1.0 --precision fp16 --scheduler euler --prompt-source synthetic --image-resolution 64 --num-images 1 --num-inference-steps 2 --guidance-scale 0 --seed 42 --prompt-len 32 --batch-size 1`

| # | Metric | Result |
|---|---|---|
| 1 | Per-image latency (per_image_latency_sec) | 0.188574 |
| 2 | Aggregate throughput (images_per_sec) | 5.302957989966804 |
| 3 | Peak VRAM, GB (peak_vram_gb) | 8.10759 |
| 4 | Denoising step time per batch, ms (step_time_ms) | 69.176542 |
| 5 | First-image latency, cold (first_image_latency_s) | 9.052455 |
<!-- /profile:smoke -->
