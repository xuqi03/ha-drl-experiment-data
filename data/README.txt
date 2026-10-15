Supplementary Data
Online UAV Path Planning for Persistent IoT Data Collection via Attention-Based Deep Reinforcement Learning
Duocheng Xu, Wenmao Zhou, and MingWei Qin

These tables provide the recorded seed-level summaries accompanying the manuscript and Supplementary Information. Each learned-policy row summarizes one training seed on the stated test instances. The deterministic heuristics have no independent training seeds. File 06 pairs original and fine-tuned results within one row for each seed. Files 01 and 02 use the primary confirmation instances. Each later experiment has its own instance set, common to methods compared within that experiment.

Units and fields
TJQoS values in files 01-07 and 09-12 are fractions from 0 to 1. Multiply by 100 to obtain the percentage shown in the manuscript. File 06 uses fixed_qos and finetuned_qos for these fractions. File 08 already expresses tjqos, completion, delivery, and loss as percentages from 0 to 100; age_gate_exceed_fraction and time_coverage_ratio remain fractions. Primary/workload plr is a fraction. AoI, packet age, delivery delay, and elapsed time use simulation time units. Queue lengths and generated/delivered/dropped volumes use packets; throughput is packets per simulation time unit. Arrival rates are packets per simulation time unit per target. The arrival-rate estimation MAE in file 07 uses the same rate units.

In file 02, avg_age is time-average AoI, max_per_source_aoi_p95 is worst-source temporal P95 AoI, episode_max_destination_aoi is episode-maximum AoI, and max_age is terminal maximum AoI. POMO was trained using 20 starting-target trajectories per instance and 20 times the HA-DRL training-trajectory count. POMO (greedy) uses one test trajectory; POMO (20 starts) denotes retrospective selection among twenty test trajectories. File 12 is a separate decoding experiment and has its own test instances; greedy_runtime and pomo_runtime are seconds per complete episode.

In file 07, the online_prior labels give the initial per-target rate estimate, and exposure_5.0 denotes five time units of equivalent initial observations. In file 11, gena keeps total expected arrivals fixed at eight packets per time unit, while genb fixes each target's arrival rate at 0.4. chosen_age_percentile_mean is the selected target's AoI rank fraction among feasible targets, pooled within each seed. Recharge choices are excluded from this rank, and ties are included. The shared N=20 condition is evaluated once.

Reward coefficient settings
File 13 gives the exact coefficients underlying the low/high reward rows in file 04 and Supplementary Section S4. Each of the seven coefficients is changed individually to 0.5 or 1.5 times its base value, with the other coefficients fixed. The terminal-failure penalty remains 1000. Duplicate selected policies identified in the Supplementary Information retain their recorded values.

Clustered spatial generation
The stress experiment uses 20 targets. The uniform condition samples target coordinates independently in the unit square. The clustered condition samples three cluster centers independently and uniformly in [0.1,0.9]^2. Each target selects one of the three centers with equal probability, then adds independent zero-mean Gaussian perturbations with standard deviation 0.08 to both coordinates. Coordinates are clipped to [0,1]. The depot remains uniformly sampled in the unit square, and each charging-station coordinate is sampled from {0,0.25,0.5,0.75,1}. The clustered-only condition keeps the base range and service settings. The joint stress condition uses this same clustered generator with the different range, station count, arrival rate, and capacity specified in the manuscript.

Identifiers
HA_FIFO/ha_fifo denote HA-DRL; CANONICAL_AM/canonical_am denote Adapted AM; ATTENTION_A2C/attention_a2c denote Attention-A2C; GAT_PPO/gat_ppo denote GAT-PPO. NO_TYPE_EMBEDDING/no_type_embedding remove the additional learned type offset; NO_CONGESTION_SUMMARY/no_congestion_summary set five scalar decoder inputs to zero: the mean and maximum normalized target queue, mean and maximum normalized target AoI, and legal-action fraction. Per-node inputs and the feasibility mask are retained. VISIT_RESET_HA/visit_reset_ha denote the visit-reset-trained control. tuned_mlp_ppo is the validation-selected MLP-PPO. Scenario standard is the base condition, tight_battery is short range, one_station changes charging-station count, and combined_harsh is the joint stress condition. Feature and reward variant names specify the input removed or coefficient changed.

File descriptions
01_primary_fifo_seed_summary.csv (35 rows): Primary FIFO confirmation test, seven learned configurations, 500 instances per training seed.
02_higher_budget_pomo_common_test.csv (15 rows): The higher-training-budget POMO checkpoints with greedy and 20-start decoding, plus HA-DRL, on the primary common instances.
03_workload_seed_summary.csv (1400 rows): 35 workload conditions; 200 common instances in each condition.
04_input_and_reward_seed_summary.csv (105 rows): Full policy, six input removals, and fourteen reward variants on their separate 500-instance test.
05_stress_seed_summary.csv (200 rows): Five spatial/range/load conditions, including learned and deterministic heuristic policies.
06_n30_finetuning_seed_summary.csv (5 rows): Paired original and fine-tuned policies on 500 N=30 instances.
07_heterogeneous_arrivals_seed_summary.csv (20 rows): Known rates and three online-estimator initializations on heterogeneous arrivals.
08_fixed_window_communication_seed_summary.csv (120 rows): Current fixed-window hover communication experiment, eight policies, three conditions, 500 instances per checkpoint and condition.
09_checkpoint_timestamp_seed_summary.csv (15 rows): Selected and epoch-100 checkpoints, midpoint and conditional-uniform timestamps, on 500 separate instances.
10_threshold_grid_seed_summary.csv (1875 rows): 125 evaluation-threshold combinations for three methods and five seeds, each using 500 instances.
11_policy_behavior_seed_summary.csv (35 rows): Seven scale/load conditions with five policies and 100 instances per condition and seed.
12_pomo_separate_decoding_test.csv (5 rows): The separate greedy and 20-start POMO decoding comparison summarized in Supplementary Section S4.
13_reward_coefficients.csv (7 rows): Seven recorded base/low/high reward coefficients; one coefficient changes at a time.
