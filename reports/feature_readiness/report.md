# Feature readiness 요약

- Target period: 2015-01-12 ~ 2026-04-23
- Target rows: 2,132
- pass_30d: 2,094
- pass_60d: 2,074
- pass_both_targets: 2,064

## Readiness 기준

- 피처는 가능한 한 넓게 수집한다.
- asof_date, 공시 lag, target horizon 이후 정보 사용 여부는 모델 투입 전에 gate로 점검한다.
- `use_now`, `derive_now`, `use_with_lag`는 첫 wide feature set 후보로 둔다.
- `review_required`는 공시 시점 검토 또는 별도 ablation에서 다룬다.
- `not_available`은 DB source 추가 후 다시 검토한다.

## 첫 wide feature source 후보
- raw.epsis_fuel_cost_monthly
- raw.epsis_power_supply_daily
- raw.epsis_power_trade_volume_monthly
- raw.epsis_smp_monthly
- raw.kma_asos_weather_daily
- raw.kma_asos_weather_station_daily
- raw.krx_ets_daily
- raw.krx_auction_monthly
- raw.commodities_monthly
- raw.eua_daily
- raw.oil_daily

## 공시 lag 검토 필요 source
- raw.gir_additional_allocation
- raw.gir_borrowing
- raw.gir_cancelled_allocation
- raw.gir_carryover
- raw.gir_certified_emissions
- raw.gir_certified_performance
- raw.gir_early_reduction
- raw.gir_methodology_status
- raw.gir_offset_issuance
- raw.gir_pre_allocation
- raw.gir_projects
- raw.gir_total_allowance
- raw.gir_unused_performance
- raw.macro_indicators
- raw.kemco_verification
- raw.khnp_allocation
- raw.kogas_emissions
- raw.kospo_emissions
- raw.kospo_intensity
- raw.kospo_scope3
- raw.kwater_emissions
