# Feature-target EDA 요약

- 분석 기간: 2015-01-12 ~ 2026-04-23
- 전체 행 수: 2,132
- 전체 feature 수: 124
- baseline 후보 feature 수: 111

## Feature group 요약
- power_epsis: 전체 46개, baseline 후보 43개, 평균 결측률 2.9%
- market_internal: 전체 36개, baseline 후보 36개, 평균 결측률 0.5%
- weather_kma: 전체 23개, baseline 후보 22개, 평균 결측률 0.0%
- external_market: 전체 10개, baseline 후보 10개, 평균 결측률 0.1%
- auction: 전체 9개, baseline 후보 0개, 평균 결측률 19.5%

## 주요 산출물
- data/processed/features/wide_features.parquet
- data/processed/features/wide_features.schema.json
- data/processed/features/wide_features.feature_meta.csv
- docs/피처_사전.md
- outputs/tables/feature_target_eda/feature_matrix_summary.csv
- outputs/tables/feature_target_eda/feature_missing_summary.csv
- outputs/tables/feature_target_eda/feature_target_ic.csv
- outputs/tables/feature_target_eda/feature_group_summary.csv
- outputs/tables/feature_target_eda/feature_drop_candidates.csv
- outputs/tables/feature_target_eda/baseline_feature_set_v1.csv
