# Djia-smart-beta
Quantitative research project on Smart Beta, factor investing, portfolio construction, and systematic equity strategies.

Overview
This project builds and compares three systematic smart-beta strategies on the Dow Jones Industrial Average (DJIA), evaluated against the DJITR (Dow Jones Total Return) benchmark.
The core idea: instead of passively replicating the price-weighted DJIA, we use machine learning to generate a monthly score for each constituent and tilt portfolio weights toward stocks with higher predicted forward returns — while staying close to the benchmark and respecting explicit risk constraints.
All three model families are evaluated on the same pipeline: same panel dataset, same forward-return target, same walk-forward out-of-sample (OOS) procedure, and the same smart_alloc allocator. This ensures a fair, benchmark-consistent comparison.

Key Design Choices
Benchmark consistency. All models are evaluated relative to DJITR, not a self-reconstructed price-weighted index. The reconstruction is validated first (correlation 0.99, annualised tracking error 1.97%) before any model is run.
Furthermore in the training period the TE gos to 1.8% as you can test in the dataset_quality.ipynb

 djia_smartbeta.ipynb          ← Main notebook (all models, full pipeline)
 djia_panel_finale_v2.csv      ← ⚠️ Required: monthly panel dataset (see below)
 djia_index_series_v2.csv      ← ⚠️ Required: DJITR total-return series (see below)
 dataset_quality.ipynb          to test and see correlation and reconstruction quality 
