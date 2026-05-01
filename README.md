# CATS Experiments Backup

Evaluation logs, demo videos, and result artifacts from the CATS (Cats Anything Task System)
work built on top of BEHAVIOR-1K. These were `.gitignore`-d in the upstream repo so they had
never been pushed; this is a snapshot taken on 2026-05-01 before cleaning the home directory.

## Original locations on the source machine

| Folder here | Original location |
|---|---|
| `behavior1k_root_experiments_cats/` | `BEHAVIOR-1K/experiments/cats/` |
| `omnigibson_experiments_cats/` | `BEHAVIOR-1K/OmniGibson/experiments/cats/` |

## Tasks covered

`micro_glass_shard_pickup`, `retrieve_egg_from_gap`, `hammer_nail`, `slatted_grill_cleaning`,
`rotate_knob_drawer`, `tilt_and_turn_window`, `tilt_to_release_bench`, `container_opening_push_turn`.

## What's inside (per run dir)

- `*.log` — runtime logs
- `*.json` — per-step states, evaluation summaries
- `*.png` — frame snapshots
- `*.mp4` — `demos_merged.mp4` (full run) and `_demo_videos/demo_NN.mp4` (per-demo)

## How to restore

CATS code itself lives in [clhaeun/EmbodiedInsightBenchmark](https://github.com/clhaeun/EmbodiedInsightBenchmark)
(the BDDL definitions, `cats_tasks/*.py`, and `llm_mock_cats_*.yaml` configs). To re-attach the
experiment outputs to a fresh checkout:

```bash
git clone https://github.com/clhaeun/EmbodiedInsightBenchmark.git
git clone https://github.com/clhaeun/cats-experiments.git
cd EmbodiedInsightBenchmark
mkdir -p experiments OmniGibson/experiments
cp -r ../cats-experiments/behavior1k_root_experiments_cats experiments/cats
cp -r ../cats-experiments/omnigibson_experiments_cats OmniGibson/experiments/cats
```
