# HA-DRL Experimental Data

Processed experimental summaries accompanying **Online UAV Path Planning for Persistent IoT Data Collection via Attention-Based Deep Reinforcement Learning**.

Authors: Duocheng Xu, Wenmao Zhou, and MingWei Qin.

This repository contains 13 CSV tables with 3,837 records, including seed-level experimental summaries and reward coefficients. These are the same data tables supplied with the manuscript. Each experiment retains its own instance set and metric units, as described in [data/README.txt](data/README.txt).

## Contents

| File | Records | Description |
| --- | ---: | --- |
| [01_primary_fifo_seed_summary.csv](data/01_primary_fifo_seed_summary.csv) | 35 | Primary FIFO confirmation test, seven learned configurations, 500 instances per training seed. |
| [02_higher_budget_pomo_common_test.csv](data/02_higher_budget_pomo_common_test.csv) | 15 | The higher-training-budget POMO checkpoints with greedy and 20-start decoding, plus HA-DRL, on the primary common instances. |
| [03_workload_seed_summary.csv](data/03_workload_seed_summary.csv) | 1400 | 35 workload conditions; 200 common instances in each condition. |
| [04_input_and_reward_seed_summary.csv](data/04_input_and_reward_seed_summary.csv) | 105 | Full policy, six input removals, and fourteen reward variants on their separate 500-instance test. |
| [05_stress_seed_summary.csv](data/05_stress_seed_summary.csv) | 200 | Five spatial/range/load conditions, including learned and deterministic heuristic policies. |
| [06_n30_finetuning_seed_summary.csv](data/06_n30_finetuning_seed_summary.csv) | 5 | Paired original and fine-tuned policies on 500 N=30 instances. |
| [07_heterogeneous_arrivals_seed_summary.csv](data/07_heterogeneous_arrivals_seed_summary.csv) | 20 | Known rates and three online-estimator initializations on heterogeneous arrivals. |
| [08_fixed_window_communication_seed_summary.csv](data/08_fixed_window_communication_seed_summary.csv) | 120 | Current fixed-window hover communication experiment, eight policies, three conditions, 500 instances per checkpoint and condition. |
| [09_checkpoint_timestamp_seed_summary.csv](data/09_checkpoint_timestamp_seed_summary.csv) | 15 | Selected and epoch-100 checkpoints, midpoint and conditional-uniform timestamps, on 500 separate instances. |
| [10_threshold_grid_seed_summary.csv](data/10_threshold_grid_seed_summary.csv) | 1875 | 125 evaluation-threshold combinations for three methods and five seeds, each using 500 instances. |
| [11_policy_behavior_seed_summary.csv](data/11_policy_behavior_seed_summary.csv) | 35 | Seven scale/load conditions with five policies and 100 instances per condition and seed. |
| [12_pomo_separate_decoding_test.csv](data/12_pomo_separate_decoding_test.csv) | 5 | The separate greedy and 20-start POMO decoding comparison summarized in Supplementary Section S4. |
| [13_reward_coefficients.csv](data/13_reward_coefficients.csv) | 7 | Seven recorded base/low/high reward coefficients; one coefficient changes at a time. |

## Reading the data

[data/README.txt](data/README.txt) defines the fields, units, comparison groups, reward settings, and spatial-generation rules. [data/data_manifest.json](data/data_manifest.json) lists file descriptions, row counts, and SHA-256 hashes.

TJQoS in the primary and most extension tables is recorded as a fraction; the fixed-window communication table records TJQoS as a percentage. Use the file-specific units in the data README when comparing the tables.

## Access

This is a private repository. Access requires explicit approval from the repository owner, **xuqi03**, followed by a GitHub collaborator invitation. Contact the owner or the corresponding author using the contact details accompanying the manuscript and provide your GitHub username. See [ACCESS.md](ACCESS.md).
