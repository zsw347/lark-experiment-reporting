---
name: lark-experiment-reporting
description: Standardize general-purpose Feishu experiment reports across machine-learning, data-science, engineering, product, scientific, and A/B experiments. Use whenever Codex creates or updates a Feishu document containing hypotheses, methods, baselines, variants, datasets, evaluation protocols, metrics, statistical tests, results, comparisons, ablations, or asks which values should be highlighted. Enforce scope and protocol boundaries, plain-language method explanations, task-appropriate metric tables, fair ranking, uncertainty reporting, traceability, and post-write verification.
---

# 飞书实验报告规范

Read [references/report-standard.md](references/report-standard.md) completely before writing or editing an experiment report.

Use the `lark-doc` skill for Feishu document operations. Preserve existing blocks, images, attachments, citations, and unrelated sections unless the user explicitly requests a rewrite.

## Required workflow

1. Identify the experiment type, objective, independent unit, target or treatment, comparison groups, and decision question. Support classification, regression, ranking or retrieval, generation, forecasting, engineering benchmarks, scientific experiments, online A/B tests, and explicitly defined custom tasks.
2. Label every result by source or role, such as official baseline, external reference, paper reproduction, project method, ablation, control, treatment, or exploratory result. Never silently merge categories with different origins or selection histories.
3. Label the evaluation protocol for every table, such as cross-validation or OOF, validation, fixed holdout Test, external evaluation, temporal backtest, offline replay, online A/B test, or another precisely defined protocol.
4. Verify source artifacts before writing. Never invent missing values, convert validation or OOF results into Test results, relabel project work as a paper reproduction, or treat offline and online results as interchangeable.
5. Explain each method in plain language from input or population through preprocessing or assignment, method or intervention, output, aggregation, and evaluation. State where fitting, tuning, randomization, and selection occur and how leakage or bias is prevented.
6. Choose task-appropriate metrics, state whether higher or lower is better, identify the primary metric, and write complete tables using the reference templates.
7. Highlight the best comparable metric cell in light green and the second-best in light yellow, independently for each metric column. Apply the same color to exact ties. Never rank across incompatible protocols, datasets, populations, result roles, or metric definitions.
8. Present preregistered, fixed-threshold, fixed-configuration, or primary results before tuned, subgroup, sensitivity, or exploratory analyses. Label all secondary analyses explicitly.
9. Add interpretation, uncertainty, limitations, decision implications, and artifact traceability. Distinguish point estimates from intervals, association from causation, and exploratory findings from locked conclusions.
10. Fetch the updated document and verify headings, table and row counts, key values, labels, metric directions, and persisted highlight colors before reporting completion.

## Non-negotiable boundaries

- Split data by the true independent unit and respect grouped or temporal dependencies; do not let related observations leak across partitions.
- Fit preprocessing, imputation, scaling, feature selection, calibration, thresholding, ensembling, and other data-dependent steps only on data permitted by the protocol.
- Keep results with different sources, protocols, datasets, populations, selection rules, or metric definitions in separate comparison pools.
- Define each primary metric, aggregation rule, uncertainty estimate, and optimization direction.
- Do not call a result a strict reproduction when required code, data, assets, hyperparameters, or protocol details were unavailable.
- Do not tune models, prompts, thresholds, variants, stopping rules, or hypotheses using the final holdout, future period, or unblinded online outcome.
