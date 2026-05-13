# METADATA

---

| 데이터 분류 | 테이블명 | 기간 | 행 수 | 컬럼 수 | 비고 |
| --- | --- | --- | --- | --- | --- |
| **KRX_ETS_DAILY** | `krx_ets_daily` | 2015-01-12 ~ 2026-04-23 | 8,213 | 12 | 장내 시세 일별 |
| **KRX_AUCTION_MONTHLY** | `krx_auction_monthly` | 2019-01-23 ~ 2026-04-08 | 80 | 12 | 경매 데이터 월별 |
| **GIR_ADDITIONAL_ALLOCATION** | `additional_allocation` | 2015 ~ 2017 | 1,371 | 7 | 추가할당량 |
| **GIR_BORROWING** | `borrowing` | 2015 ~ 2024 | 800 | 7 | 배출권 차입량 |
| **GIR_CANCELLED_ALLOCATION** | `cancelled_allocation` | 2015 ~ 2030 | 9,583 | 7 | 할당 취소량 |
| **GIR_CARRYOVER** | `carryover` | 2015, 2018, 2021 | 1,228 | 8 | 배출권 이월량 |
| **GIR_CERTIFIED_EMISSIONS** | `certified_emissions` | 2015 ~ 2025 | 8,156 | 7 | 인증 배출량 |
| **GIR_CERTIFIED_PERFORMANCE** | `certified_performance` | 2013 ~ 2025 | 1,593 | 10 | 감축사업 인증실적 |
| **GIR_EARLY_REDUCTION** | `early_reduction` | 2012 ~ 2013 | 914 | 7 | 조기감축실적 할당량 |
| **GIR_GIR_PROJECTS** | `gir_projects` | 2013 ~ 2025 | 1,389 | 8 | 감축사업 등록 |
| **GIR_METHODOLOGY_STATUS** | `methodology_status` | 2015 ~ 2026 | 322 | 10 | 감축방법론 목록 |
| **GIR_OFFSET_ISSUANCE** | `offset_issuance` | 2015 ~ 2026 | 331 | 7 | 상쇄배출권 발행량 |
| **GIR_PRE_ALLOCATION** | `pre_allocation` | 2015 ~ 2030 | 12,009 | 8 | 사전할당량 |
| **GIR_TOTAL_ALLOWANCE** | `total_allowance` | 2015 ~ 2030 | 16 | 4 | 전체 시장 총량 |
| **GIR_UNUSED_PERFORMANCE** | `unused_performance` | 2013 ~ 2025 | 76 | 9 | 국내 미사용 CER |
| **OIL_DAILY** | `oil_daily` | 2015-01-02 ~ 2026-04-23 | 2,844 | 4 | 원유 일별 |
| **COMMODITIES_MONTHLY** | `commodities_monthly` | 2015-01-01 ~ 2026-04-01 | 136 | 5 | 비원유 월별 |
| **MACRO_INDICATORS** | `macro_indicators` | 2015-01-01 ~ 2026-04-24 | 2,949 | 4 | 거시경제 지표 |
| **EUA_DAILY** | `eua_daily` | 2015-01-02 ~ 2026-05-04 | 2,912 | 7 | EU 탄소배출권(EUA) 선물 일별 |
| **KHNP_ALLOCATION** | `khnp_allocation` | 2015 ~ 2025 | 7 | 4 | 한수원 할당량 |
| **KOGAS_EMISSIONS** | `kogas_emissions` | 2018 ~ 2024 | 26 | 7 | 가스공사 배출량 (연간 + 부문별) |
| **KOSPO_EMISSIONS** | `kospo_emissions` | 2016 ~ 2024 | 200 | 5 | 동서발전 배출량 (Scope1/2) |
| **KOSPO_INTENSITY** | `kospo_intensity` | 2016 ~ 2024 | 108 | 5 | 동서발전 원단위 (월별) |
| **KOSPO_SCOPE3** | `kospo_scope3` | 2020 ~ 2023 | 4 | 6 | 동서발전 배출량 (Scope3) |
| **KWATER_EMISSIONS** | `kwater_emissions` | 2016 ~ 2024 | 10 | 6 | 수자원공사 배출량 |
| **KEMCO_VERIFICATION** | `verification` | 2023 ~ 2031 | 874 | 14 | 한국에너지공단 검증 |
| **EPSIS_POWER_SUPPLY_DAILY** | `epsis_power_supply_daily` | 2015-01-01 ~ 2025-12-31 | 4,018 | 19 | P2/P3 external raw: 일별 전력수급 |
| **EPSIS_SMP_MONTHLY** | `epsis_smp_monthly` | 2015-01-01 ~ 2025-12-01 | 132 | 16 | P2/P3 external raw: 월별 SMP |
| **EPSIS_FUEL_COST_MONTHLY** | `epsis_fuel_cost_monthly` | 2015-01-01 ~ 2025-12-01 | 132 | 27 | P2/P3 external raw: 월별 연료비 |
| **EPSIS_POWER_TRADE_VOLUME_MONTHLY** | `epsis_power_trade_volume_monthly` | 2015-01-01 ~ 2025-12-01 | 132 | 31 | P2/P3 external raw: 월별 전력거래량 |
| **KMA_ASOS_WEATHER_STATION_DAILY** | `kma_asos_weather_station_daily` | 2015-01-01 ~ 2025-12-31 | 24,108 | 18 | P2/P3 external raw: station-level 일별 기상 |
| **KMA_ASOS_WEATHER_DAILY** | `kma_asos_weather_daily` | 2015-01-01 ~ 2025-12-31 | 4,018 | 17 | P2/P3 external raw: aggregate 일별 기상 |

---

## 1. KRX_ETS_DAILY (장내 시세 일별)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `krx_ets_daily` |
| **기간** | 2015-01-12 ~ 2026-04-23 |
| **행 수** | 8,213 행 |
| **컬럼 수** | 12 |
| **출처** | 한국거래소 배출권시장 |
| **파일** | `data/raw/krx/krx_ets_daily.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `period` | INTEGER | 계획기간 | 1, 2, 3, 4 | 연도 기준 매핑 |
| `trd_dd` | DATE | 거래일 | YYYY-MM-DD | KRX 원본 유지 (Trade Date) |
| `isu_code` | VARCHAR | 종목코드 |  | KAU15, KAU16, … (할당연도) |
| `clsprc` | INTEGER | 종가 | KRW/톤 |  |
| `chgh` | INTEGER | 전일대비 | KRW/톤 |  |
| `chgh_rt` | NUMERIC | 전일대비 등락률 | % |  |
| `opr` | INTEGER | 시가 | KRW/톤 |  |
| `hpr` | INTEGER | 고가 | KRW/톤 |  |
| `lpr` | INTEGER | 저가 | KRW/톤 |  |
| `acc_trdvol` | INTEGER | 누적거래량 | 톤 |  |
| `acc_trdval` | INTEGER | 누적거래대금 | KRW |  |
| `vwap` | INTEGER | 거래량가중평균가 | KRW/톤 | VWAP |

---

## 2. KRX_AUCTION_MONTHLY (경매 데이터 월별)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `krx_auction_monthly` |
| **기간** | 2019-01-23 ~ 2026-04-08 |
| **행 수** | 80 행 |
| **컬럼 수** | 12 |
| **출처** | 한국거래소 배출권 경매 |
| **파일** | `data/raw/krx/krx_auction_monthly.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `period` | INTEGER | 계획기간 | 2, 3, 4 | 연도 기준 매핑 |
| `trd_dd` | DATE | 경매일 | YYYY-MM-DD | KRX 원본 유지 (Trade Date) |
| `isu_code` | VARCHAR | 종목코드 |  | KAU18, KAU19, … (할당연도) |
| `onewayauct_appl_qty` | INTEGER | 단방향 경매 신청수량 | 톤 |  |
| `auct_trd_qty` | INTEGER | 경매 체결수량 | 톤 |  |
| `auct_trd_rto` | NUMERIC | 경매 체결률 | % |  |
| `auct_trd_partc_cnt` | INTEGER | 경매 참여자수 | 명 |  |
| `acc_trdcnt` | INTEGER | 누적주문건수 | 건 |  |
| `hgst_ord_prc` | INTEGER | 최고주문가격 | KRW/톤 |  |
| `lwst_ord_prc` | INTEGER | 최저주문가격 | KRW/톤 |  |
| `acc_trdvol` | INTEGER | 누적거래량 | 톤 |  |
| `clsprc` | INTEGER | 낙찰가 | KRW/톤 |  |

---

## 3. GIR_ADDITIONAL_ALLOCATION (추가할당량)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `additional_allocation` |
| **기간** | 2015 ~ 2017 |
| **행 수** | 1,371 행 |
| **컬럼 수** | 7 |
| **출처** | 한국기후·환경연구원 (GIR) |
| **파일** | `data/raw/public/gir/additional_allocation.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `period` | INTEGER | 계획기간 | 1 | 1 기 (2015-2017) 만 존재 |
| `year` | INTEGER | 연도 | YYYY | 2015, 2016, 2017 |
| `no` | INTEGER | 순번 |  | 업체 식별 번호 |
| `sector` | VARCHAR | 부문 |  | 수송, 전환, 산업 등 |
| `industry` | VARCHAR | 업종 |  | 항공, 집단에너지 등 |
| `company_name` | VARCHAR | 업체명 |  |  |
| `allocation_qty` | INTEGER | 추가할당량 | 톤 | wide→long 변환됨 |

---

## 4. GIR_BORROWING (배출권 차입량)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `borrowing` |
| **기간** | 2015 ~ 2024 |
| **행 수** | 800 행 |
| **컬럼 수** | 7 |
| **출처** | 한국기후·환경연구원 (GIR) |
| **파일** | `data/raw/public/gir/borrowing.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `period` | INTEGER | 계획기간 | 1, 2, 3 | 1 기=267, 2 기=267, 3 기=266 행 |
| `year` | INTEGER | 연도 | YYYY | 2015~2024 |
| `no` | INTEGER | 순번 |  | 업체 식별 번호 |
| `sector` | VARCHAR | 부문 |  | 산업, 건물, 수송 등 |
| `industry` | VARCHAR | 업종 |  | 시멘트, 제지, 철강 등 |
| `company_name` | VARCHAR | 업체명 |  |  |
| `borrowing_qty` | INTEGER | 배출권 차입량 | 톤 |  |

---

## 5. GIR_CANCELLED_ALLOCATION (할당 취소량)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `cancelled_allocation` |
| **기간** | 2015 ~ 2030 |
| **행 수** | 9,583 행 |
| **컬럼 수** | 7 |
| **출처** | 한국기후·환경연구원 (GIR) |
| **파일** | `data/raw/public/gir/cancelled_allocation.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `period` | INTEGER | 계획기간 | 1, 2, 3, 4 | 1 기=1,597, 2 기=2,007, 3 기=4,255, 4 기=1,724 행 |
| `year` | INTEGER | 연도 | YYYY | 2015~2030 |
| `no` | INTEGER | 순번 |  | 업체 식별 번호 |
| `sector` | VARCHAR | 부문 |  | 산업, 건물, 수송 등 |
| `industry` | VARCHAR | 업종 |  | 철강, 제지, 시멘트 등 |
| `company_name` | VARCHAR | 업체명 |  |  |
| `cancelled_qty` | INTEGER | 할당 취소량 | 톤 | 0 행 포함 (원본 특성) |

---

## 6. GIR_CARRYOVER (배출권 이월량)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `carryover` |
| **기간** | 2015, 2018, 2021 |
| **행 수** | 1,228 행 |
| **컬럼 수** | 8 |
| **출처** | 한국기후·환경연구원 (GIR) |
| **파일** | `data/raw/public/gir/carryover.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `period` | INTEGER | 계획기간 | 1, 2, 3 | 1 기=409, 2 기=409, 3 기=410 행 |
| `year` | INTEGER | 연도 | YYYY | 2015, 2018, 2021 |
| `no` | INTEGER | 순번 |  | 업체 식별 번호 |
| `sector` | VARCHAR | 부문 |  | 산업, 건물, 수송 등 |
| `industry` | VARCHAR | 업종 |  | 석유화학, 철강, 시멘트 등 |
| `company_name` | VARCHAR | 업체명 |  |  |
| `carryover_qty` | INTEGER | 배출권 이월량 | 톤 | 당해 연도 미사용 배출권 |
| `banking_qty` | INTEGER | 상환배출권 수량 | 톤 | 은행적립량 |

---

## 7. GIR_CERTIFIED_EMISSIONS (인증 배출량)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `certified_emissions` |
| **기간** | 2015 ~ 2025 |
| **행 수** | 8,156 행 |
| **컬럼 수** | 7 |
| **출처** | 한국기후·환경연구원 (GIR) |
| **파일** | `data/raw/public/gir/certified_emissions.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `period` | INTEGER | 계획기간 | 1, 2, 3 | 1 기=1,878, 2 기=2,013, 3 기=4,265 행 |
| `year` | INTEGER | 연도 | YYYY | 2015~2025 |
| `no` | INTEGER | 순번 |  | 업체 식별 번호 |
| `sector` | VARCHAR | 부문 |  | 산업, 건물, 수송 등 |
| `industry` | VARCHAR | 업종 |  | 음식료품, 목재, 철강 등 |
| `company_name` | VARCHAR | 업체명 |  |  |
| `certified_emissions_qty` | NUMERIC | 인증 배출량 | 톤 | 실제 배출량 (MRV 인증) |

---

## 8. GIR_CERTIFIED_PERFORMANCE (감축사업 인증실적)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `certified_performance` |
| **기간** | 2013 ~ 2025 |
| **행 수** | 1,593 행 |
| **컬럼 수** | 10 |
| **출처** | 한국기후·환경연구원 (GIR) |
| **파일** | `data/raw/public/gir/certified_performance.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `period` | INTEGER | 계획기간 | 0, 1, 2, 3 | validity_period 에서 매핑 |
| `no` | INTEGER | 번호 |  | 사업 식별 번호 |
| `project_name` | VARCHAR | 사업명 |  | 감축사업 이름 |
| `company_name` | VARCHAR | 업체명 |  | 사업 시행 업체 |
| `certified_qty` | INTEGER | 온실가스감축량 | tCO2-eq | 인증받은 감축량 |
| `validity_period` | VARCHAR | 유효기간 |  | 사업 인증 유효기간 |
| `monitoring_info` | VARCHAR | 모니터링차수 |  | 제 X 차 모니터링 기간 |
| `certification_no` | VARCHAR | 인증실적고유번호 |  | 인증 번호 |
| `cdm_type` | VARCHAR | CDM 구분 |  | 일반/심화 등 (608 행 NaN) |
| `region` | VARCHAR | 지역 | domestic/overseas | 국내 + 해외 통합 |

---

## 9. GIR_EARLY_REDUCTION (조기감축실적 할당량)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `early_reduction` |
| **기간** | 2012 ~ 2013 |
| **행 수** | 914 행 |
| **컬럼 수** | 7 |
| **출처** | 한국기후·환경연구원 (GIR) |
| **파일** | `data/raw/public/gir/early_reduction.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `period` | INTEGER | 계획기간 | 0 | ETS 이전 (조기감축) |
| `year` | INTEGER | 연도 | YYYY | 2012, 2013 |
| `no` | INTEGER | 순번 |  | 업체 식별 번호 |
| `sector` | VARCHAR | 부문 |  | 수송, 전환, 산업 등 |
| `industry` | VARCHAR | 업종 |  | 항공, 집단에너지 등 |
| `company_name` | VARCHAR | 업체명 |  |  |
| `early_reduction_qty` | INTEGER | 조기감축실적 할당량 | 톤 | ETS 이전 실적 인정분 |

---

## 10. GIR_GIR_PROJECTS (감축사업 등록)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `gir_projects` |
| **기간** | 2013 ~ 2025 |
| **행 수** | 1,389 행 |
| **컬럼 수** | 8 |
| **출처** | 한국기후·환경연구원 (GIR) |
| **파일** | `data/raw/public/gir/gir_projects.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `period` | INTEGER | 계획기간 | 0, 1, 2, 3 | validity_period 에서 매핑 |
| `no` | INTEGER | 번호 |  | 사업 식별 번호 |
| `project_name` | VARCHAR | 사업명 |  | 감축사업 이름 |
| `company_name` | VARCHAR | 업체명 |  | 사업 시행 업체 |
| `validity_period` | VARCHAR | 유효기간 |  | 사업 인증 유효기간 |
| `methodology` | VARCHAR | 방법론 |  | 감축방법론 |
| `cdm_type` | VARCHAR | CDM 구분 |  | 일반/심화 등 |
| `region` | VARCHAR | 지역 | domestic/overseas | domestic 1,116 행, overseas 273 행 |

---

## 11. GIR_METHODOLOGY_STATUS (감축방법론 목록)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `methodology_status` |
| **기간** | 2015-04-21 ~ 2026-03-05 |
| **행 수** | 322 행 |
| **컬럼 수** | 10 |
| **출처** | 한국기후·환경연구원 (GIR) |
| **파일** | `data/raw/public/gir/methodology_status.csv` |
| **인코딩** | utf-8-sig |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `no` | INTEGER | 방법론 번호 |  |  |
| `methodology_name` | VARCHAR | 방법론 이름 |  |  |
| `new_or_revised` | VARCHAR | 신규 또는 개정 |  |  |
| `methodology_field` | VARCHAR | 분야 분류 |  | 산림, 에너지, 산업공정 등 |
| `methodology_id` | VARCHAR | 고유번호 |  | 1 행 NaN |
| `validity_start_date` | DATE | 유효시작일 | YYYY-MM-DD |  |
| `first_validity_start_date` | DATE | 최초유효시작일 | YYYY-MM-DD | ‘-’ 문자 포함 |
| `methodology_type` | VARCHAR | 종류 |  |  |
| `registration_type` | VARCHAR | 등록형태 |  |  |
| `authority` | VARCHAR | 관장기관 |  | 산업통상부, 기후에너지환경부 |

---

## 12. GIR_OFFSET_ISSUANCE (상쇄배출권 발행량)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `offset_issuance` |
| **기간** | 2015 ~ 2026 |
| **행 수** | 331 행 |
| **컬럼 수** | 7 |
| **출처** | 한국기후·환경연구원 (GIR) |
| **파일** | `data/raw/public/gir/offset_issuance.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `period` | INTEGER | 계획기간 | 1, 2, 3, 4 | 1 기=144, 2 기=35, 3 기=151, 4 기=1 행 |
| `year` | INTEGER | 연도 | YYYY | 2015~2026 |
| `no` | INTEGER | 순번 |  | 업체 식별 번호 |
| `sector` | VARCHAR | 부문 |  | 전환, 산업 등 |
| `industry` | VARCHAR | 업종 |  | 증기, 냉온수 등 |
| `company_name` | VARCHAR | 업체명 |  |  |
| `offset_qty` | INTEGER | 상쇄배출권 발행량 | 톤 |  |

---

## 13. GIR_PRE_ALLOCATION (사전할당량)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `pre_allocation` |
| **기간** | 2015 ~ 2030 |
| **행 수** | 12,009 행 |
| **컬럼 수** | 8 |
| **출처** | 한국기후·환경연구원 (GIR) |
| **파일** | `data/raw/public/gir/pre_allocation.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `no` | INTEGER | 순번 |  | 업체 식별 번호 |
| `sector` | VARCHAR | 부문 |  | 발전·에너지, 산업 등 |
| `company_name` | VARCHAR | 업체명 |  |  |
| `period` | INTEGER | 계획기간 | 1, 2, 3, 4 |  |
| `year` | INTEGER | 연도 | YYYY | 2015~2030 |
| `pre_allocation_qty` | NUMERIC | 사전할당량 | 톤 |  |
| `industry` | VARCHAR | 업종 |  | 6,813 행 NaN |
| `allocation_type` | VARCHAR | 할당유형 |  | 6,813 행 NaN |

---

## 14. GIR_TOTAL_ALLOWANCE (전체 시장 총량)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `total_allowance` |
| **기간** | 2015 ~ 2030 |
| **행 수** | 16 행 |
| **컬럼 수** | 4 |
| **출처** | 한국기후·환경연구원 (GIR) |
| **파일** | `data/raw/public/gir/total_allowance.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `period` | INTEGER | 계획기간 | 1, 2, 3, 4 |  |
| `year` | INTEGER | 연도 | YYYY | 2015~2030 |
| `total_emissions` | INTEGER | 총배출량 | 톤 | 시장 전체 |
| `total_allowance_qty` | INTEGER | 총할당량 | 톤 | 시장 전체 |

---

## 15. GIR_UNUSED_PERFORMANCE (국내 미사용 CER)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `unused_performance` |
| **기간** | 2020 ~ 2024 |
| **행 수** | 76 행 |
| **컬럼 수** | 9 |
| **출처** | 한국기후·환경연구원 (GIR) |
| **파일** | `data/raw/public/gir/unused_performance.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `period` | INTEGER | 계획기간 | 1, 2, 3 | 3 기=75, 1 기=1 행 |
| `no` | INTEGER | 번호 |  | 사업 식별 번호 |
| `project_name` | VARCHAR | 사업명 |  | 감축사업 이름 |
| `project_name_en` | VARCHAR | 사업명 (영문) |  |  |
| `unused_qty` | INTEGER | 미사용량 | 톤 | 무효화된 CER |
| `monitoring_period` | VARCHAR | 모니터링 기간 |  |  |
| `invalidation_date` | DATE | 무효화일 | YYYY-MM-DD |  |
| `serial_no` | VARCHAR | 일련번호 |  |  |
| `public_yn` | VARCHAR | 공개여부 |  | 1 행 NaN |

---

## 16. OIL_DAILY (원유 일별)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `oil_daily` |
| **기간** | 2015-01-02 ~ 2026-04-23 |
| **행 수** | 2,844 행 |
| **컬럼 수** | 4 |
| **출처** | 에너지경제연구원 |
| **파일** | `data/raw/energy/oil_daily.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `period` | INTEGER | 계획기간 | 1, 2, 3, 4 | 연도 기준 매핑 |
| `date` | DATE | 거래일 | YYYY-MM-DD |  |
| `WTI` | NUMERIC | 서부텍사스산 원유 | USD/배럴 |  |
| `Brent` | NUMERIC | 브렌트산 원유 | USD/배럴 |  |

---

## 17. COMMODITIES_MONTHLY (비원유 월별)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `commodities_monthly` |
| **기간** | 2015-01-01 ~ 2026-04-01 |
| **행 수** | 136 행 |
| **컬럼 수** | 5 |
| **출처** | 에너지경제연구원 |
| **파일** | `data/raw/energy/commodities_monthly.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `period` | INTEGER | 계획기간 | 1, 2, 3, 4 | 연도 기준 매핑 |
| `date` | DATE | 기준일 | YYYY-MM-DD | 월별 |
| `LNG_Japan` | NUMERIC | LNG 수입가격 (일본) | USD/MBtu |  |
| `NatGas_Europe` | NUMERIC | 천연가스 가격 (유럽) | USD/MBtu |  |
| `Coal_Newcastle` | NUMERIC | 석탄 가격 (뉴캐슬) | USD/톤 |  |

---

## 18. MACRO_INDICATORS (거시경제 지표)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `macro_indicators` |
| **기간** | 2015-01-01 ~ 2026-04-24 |
| **행 수** | 2,949 행 |
| **컬럼 수** | 4 |
| **출처** | 거시경제 지표 |
| **파일** | `data/raw/macro/macro_daily.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `period` | INTEGER | 계획기간 | 1, 2, 3, 4 | 연도 기준 매핑 |
| `date` | DATE | 기준일 | YYYY-MM-DD |  |
| `KOSPI` | NUMERIC | 코스피 지수 | point |  |
| `USDKRW` | NUMERIC | 원/달러 환율 | KRW/USD |  |

---

## 19. KHNP_ALLOCATION (한수원 할당량)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `khnp_allocation` |
| **기간** | 2015 ~ 2025 |
| **행 수** | 7 행 |
| **컬럼 수** | 4 |
| **출처** | 한국수력원자력 |
| **파일** | `data/processed/public/khnp/khnp_allocation.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `period` | INTEGER | 계획기간 | 1, 2, 3, 4 | 연도 기준 매핑 |
| `year` | INTEGER | 연도 | YYYY | |
| `unit` | VARCHAR | 사업장/호기 | | |
| `free_allocation_qty` | NUMERIC | 무상할당량 | 톤 | |

---

## 20. KOGAS_EMISSIONS (가스공사 배출량)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `kogas_emissions` |
| **기간** | 2018 ~ 2024 |
| **행 수** | 26 행 |
| **컬럼 수** | 7 |
| **출처** | 한국가스공사 |
| **파일** | `data/processed/public/kogas/kogas_emissions.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `period` | INTEGER | 계획기간 | 1, 2, 3, 4 | 연도 기준 매핑 |
| `year` | INTEGER | 연도 | YYYY | |
| `data_type` | VARCHAR | 데이터 타입 | | 실적, 목표 등 |
| `sector` | VARCHAR | 부문 | | 공통, 발전 등 |
| `total_emissions` | NUMERIC | 총 배출량 | 톤 | |
| `direct_emissions` | NUMERIC | 직접 배출량 | 톤 | |
| `indirect_emissions` | NUMERIC | 간접 배출량 | 톤 | |

---

## 21. KOSPO_EMISSIONS (동서발전 배출량)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `kospo_emissions` |
| **기간** | 2016 ~ 2024 |
| **행 수** | 200 행 |
| **컬럼 수** | 5 |
| **출처** | 한국동서발전 |
| **파일** | `data/processed/public/kospo/kospo_emissions.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `period` | INTEGER | 계획기간 | 1, 2, 3, 4 | 연도 기준 매핑 |
| `year` | INTEGER | 연도 | YYYY | |
| `category` | VARCHAR | 분류 | | 발전소명 등 |
| `scope` | VARCHAR | Scope | | Scope 1, Scope 2 |
| `emissions` | NUMERIC | 배출량 | 톤 | |

---

## 22. KOSPO_INTENSITY (동서발전 원단위)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `kospo_intensity` |
| **기간** | 2016 ~ 2024 |
| **행 수** | 108 행 |
| **컬럼 수** | 5 |
| **출처** | 한국동서발전 |
| **파일** | `data/processed/public/kospo/kospo_intensity.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `period` | INTEGER | 계획기간 | 1, 2, 3, 4 | 연도 기준 매핑 |
| `year` | INTEGER | 연도 | YYYY | |
| `month` | INTEGER | 월 | MM | |
| `category` | VARCHAR | 분류 | | 원단위 대상 |
| `intensity` | NUMERIC | 온실가스 배출 원단위 | | |

---

## 23. KOSPO_SCOPE3 (동서발전 Scope3)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `kospo_scope3` |
| **기간** | 2020 ~ 2023 |
| **행 수** | 4 행 |
| **컬럼 수** | 6 |
| **출처** | 한국동서발전 |
| **파일** | `data/processed/public/kospo/kospo_scope3.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `period` | INTEGER | 계획기간 | 1, 2, 3, 4 | 연도 기준 매핑 |
| `year` | INTEGER | 연도 | YYYY | |
| `no` | INTEGER | 순번 | | |
| `category_count` | INTEGER | 대상 카테고리 수 | | |
| `scope3_emissions` | NUMERIC | Scope 3 배출량 | 톤 | |
| `voluntary_verification` | VARCHAR | 자발적 검증 여부 | | |

---

## 24. KWATER_EMISSIONS (수자원공사 배출량)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `kwater_emissions` |
| **기간** | 2016 ~ 2024 |
| **행 수** | 10 행 |
| **컬럼 수** | 6 |
| **출처** | 한국수자원공사 |
| **파일** | `data/processed/public/kwater/kwater_emissions.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `period` | INTEGER | 계획기간 | 1, 2, 3, 4 | 연도 기준 매핑 |
| `year` | INTEGER | 연도 | YYYY | |
| `allowance_qty` | NUMERIC | 할당량 | 톤 | |
| `emissions_qty` | NUMERIC | 배출량 | 톤 | |
| `compliance_qty` | NUMERIC | 배출권 제출량 | 톤 | |
| `compliance_rate` | NUMERIC | 제출 달성률 | % | |

---

## 25. KEMCO_VERIFICATION (한국에너지공단 검증)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `verification` |
| **기간** | 2023 ~ 2031 |
| **행 수** | 874 행 |
| **컬럼 수** | 14 |
| **출처** | 한국에너지공단 |
| **파일** | `data/processed/public/kemco/verification.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `period` | INTEGER | 계획기간 | 1, 2, 3, 4 | 연도 기준 매핑 |
| `ctfcn_year` | INTEGER | 인증연도 | YYYY | |
| `ctfcn_date` | DATE | 인증일자 | YYYY-MM-DD | |
| `data_reg_dt` | DATE | 데이터등록일 | YYYY-MM-DD | |
| `vld_ymd` | DATE | 유효시작일 | YYYY-MM-DD | |
| `no` | INTEGER | 연번 | | |
| `vrfc_ctfcn_no` | VARCHAR | 검증인증번호 | | |
| `vrfc_cd` | VARCHAR | 검증코드 | | |
| `bizent_nm` | VARCHAR | 기업명 | | |
| `fctr_nm` | VARCHAR | 공장명/사업장명 | | |
| `mdl_nm` | VARCHAR | 모델명 | | |
| `mdul_otpt_qnty` | NUMERIC | 모듈출력량 | W | |
| `crbn_emqty` | NUMERIC | 탄소배출량 | kgCO2 | |
| `vrfc_way` | VARCHAR | 검증방식 | | |

---

## 26. EUA_DAILY (EU 탄소배출권 선물 일별)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `eua_daily` |
| **기간** | 2015-01-02 ~ 2026-05-04 |
| **행 수** | 2,912 행 |
| **컬럼 수** | 7 |
| **출처** | Investing.com (ICE EUA Futures) |
| **파일** | `data/raw/macro/eua_daily.csv` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `period` | INTEGER | 계획기간 | 1, 2, 3, 4 | 연도 기준 매핑 |
| `date` | DATE | 거래일 | YYYY-MM-DD | |
| `clsprc` | NUMERIC | 종가 | EUR/톤 | |
| `opr` | NUMERIC | 시가 | EUR/톤 | |
| `hpr` | NUMERIC | 고가 | EUR/톤 | |
| `lpr` | NUMERIC | 저가 | EUR/톤 | |
| `acc_trdvol` | NUMERIC | 거래량 | 계약 수 | K/M 단위 변환 완료 |

---

## 27. EPSIS_POWER_SUPPLY_DAILY (일별 전력수급)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `epsis_power_supply_daily` |
| **기간** | 2015-01-01 ~ 2025-12-31 |
| **행 수** | 4,018 행 |
| **컬럼 수** | 19 |
| **출처** | EPSIS/KPX 전력수급실적 |
| **파일** | `data/processed/features/epsis_power_supply_daily.parquet` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `feature_date` | DATE | 관측 기준일 | YYYY-MM-DD | EPSIS 원 관측일 |
| `asof_date` | DATE | 모델 사용 가능일 | YYYY-MM-DD | 일별 T+1 보수적 공개 지연 적용 |
| `year` | VARCHAR | 관측 연도 | YYYY | 원 응답 기준 |
| `month` | VARCHAR | 관측 월 | MM | 원 응답 기준 |
| `day` | VARCHAR | 관측 일 | DD | 원 응답 기준 |
| `installed_capacity_mw` | NUMERIC | 설비용량 | MW | 전력계통 설비 기준 |
| `supply_capacity_mw` | NUMERIC | 공급능력 | MW | 당일 공급 가능 용량 |
| `peak_demand_mw` | NUMERIC | 최대전력수요 | MW | 피크 수요 |
| `minimum_demand_mw` | NUMERIC | 최소전력수요 | MW | 일부 기간 결측 |
| `minimum_demand_datetime_text` | VARCHAR | 최소전력수요 발생시각 | 원문 문자열 | 일부 기간 결측 |
| `reserve_capacity_mw` | NUMERIC | 공급예비력 | MW | 공급능력 - 최대전력수요 |
| `reserve_margin_pct` | NUMERIC | 공급예비율 | % | 공급예비력 / 최대전력수요 |
| `peak_demand_datetime_text` | VARCHAR | 최대전력수요 발생시각 | 원문 문자열 | 예: `2015/01/02(11:00)` |
| `source` | VARCHAR | 자료 출처 |  | `EPSIS/KPX` |
| `source_label_ko` | VARCHAR | 원천 화면명 |  | 전력수급실적 |
| `source_url` | VARCHAR | 수집 엔드포인트 | URL | EPSIS AJAX endpoint |
| `frequency` | VARCHAR | 주기 |  | daily |
| `disclosure_lag_rule` | VARCHAR | 공개 지연 규칙 |  | `daily_t_plus_1_conservative` |
| `retrieved_at_utc` | VARCHAR | 수집 시각 | UTC | ISO-8601 문자열 |

---

## 28. EPSIS_SMP_MONTHLY (월별 SMP)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `epsis_smp_monthly` |
| **기간** | 2015-01-01 ~ 2025-12-01 |
| **행 수** | 132 행 |
| **컬럼 수** | 16 |
| **출처** | EPSIS/KPX 가중평균SMP |
| **파일** | `data/processed/features/epsis_smp_monthly.parquet` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `feature_date` | DATE | 월 관측 기준일 | YYYY-MM-DD | 해당 월 1일 |
| `feature_month` | DATE | 관측 월 | YYYY-MM-DD | 월별 key |
| `asof_date` | DATE | 모델 사용 가능일 | YYYY-MM-DD | M+1 월말 보수적 공개 지연 적용 |
| `year` | VARCHAR | 관측 연도 | YYYY | 원 응답 기준 |
| `month` | VARCHAR | 관측 월 | MM | 원 응답 기준 |
| `Period` | VARCHAR | 원천 기간 문자열 | YYYY/MM | EPSIS 원 컬럼명 유지 |
| `smp_land_krw_per_kwh` | NUMERIC | 육지 가중평균 SMP | KRW/kWh |  |
| `smp_jeju_krw_per_kwh` | NUMERIC | 제주 가중평균 SMP | KRW/kWh |  |
| `smp_total_krw_per_kwh` | NUMERIC | 전체 가중평균 SMP | KRW/kWh | 육지+제주 통합 |
| `blmp_krw_per_kwh` | NUMERIC | BLMP | KRW/kWh | 원천 제공 보조 가격 |
| `source` | VARCHAR | 자료 출처 |  | `EPSIS/KPX` |
| `source_label_ko` | VARCHAR | 원천 화면명 |  | 가중평균SMP |
| `source_url` | VARCHAR | 수집 엔드포인트 | URL | EPSIS AJAX endpoint |
| `frequency` | VARCHAR | 주기 |  | monthly |
| `disclosure_lag_rule` | VARCHAR | 공개 지연 규칙 |  | `monthly_m_plus_1_end_conservative` |
| `retrieved_at_utc` | VARCHAR | 수집 시각 | UTC | ISO-8601 문자열 |

---

## 29. EPSIS_FUEL_COST_MONTHLY (월별 연료비)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `epsis_fuel_cost_monthly` |
| **기간** | 2015-01-01 ~ 2025-12-01 |
| **행 수** | 132 행 |
| **컬럼 수** | 27 |
| **출처** | EPSIS/KPX 연료비용 |
| **파일** | `data/processed/features/epsis_fuel_cost_monthly.parquet` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `feature_date` | DATE | 월 관측 기준일 | YYYY-MM-DD | 해당 월 1일 |
| `feature_month` | DATE | 관측 월 | YYYY-MM-DD | 월별 key |
| `asof_date` | DATE | 모델 사용 가능일 | YYYY-MM-DD | M+1 월말 보수적 공개 지연 적용 |
| `year` | VARCHAR | 관측 연도 | YYYY | 원 응답 기준 |
| `month` | VARCHAR | 관측 월 | MM | 원 응답 기준 |
| `Period` | VARCHAR | 원천 기간 문자열 | YYYY/MM | EPSIS 원 컬럼명 유지 |
| `fuel_price_nuclear_krw_per_kwh` | NUMERIC | 원자력 연료가격 | KRW/kWh |  |
| `fuel_price_bituminous_coal_krw_per_ton` | NUMERIC | 유연탄 연료가격 | KRW/톤 |  |
| `fuel_price_anthracite_krw_per_ton` | NUMERIC | 무연탄 연료가격 | KRW/톤 |  |
| `fuel_price_oil_krw_per_kl` | NUMERIC | 유류 연료가격 | KRW/kL |  |
| `fuel_price_lng_krw_per_ton` | NUMERIC | LNG 연료가격 | KRW/톤 |  |
| `heat_price_nuclear_krw_per_gcal` | NUMERIC | 원자력 열량단가 | KRW/Gcal |  |
| `heat_price_bituminous_coal_krw_per_gcal` | NUMERIC | 유연탄 열량단가 | KRW/Gcal |  |
| `heat_price_anthracite_krw_per_gcal` | NUMERIC | 무연탄 열량단가 | KRW/Gcal |  |
| `heat_price_oil_krw_per_gcal` | NUMERIC | 유류 열량단가 | KRW/Gcal |  |
| `heat_price_lng_krw_per_gcal` | NUMERIC | LNG 열량단가 | KRW/Gcal |  |
| `fuel_cost_nuclear_krw_per_kwh` | NUMERIC | 원자력 발전연료비 | KRW/kWh |  |
| `fuel_cost_bituminous_coal_krw_per_kwh` | NUMERIC | 유연탄 발전연료비 | KRW/kWh |  |
| `fuel_cost_anthracite_krw_per_kwh` | NUMERIC | 무연탄 발전연료비 | KRW/kWh |  |
| `fuel_cost_oil_krw_per_kwh` | NUMERIC | 유류 발전연료비 | KRW/kWh |  |
| `fuel_cost_lng_krw_per_kwh` | NUMERIC | LNG 발전연료비 | KRW/kWh |  |
| `source` | VARCHAR | 자료 출처 |  | `EPSIS/KPX` |
| `source_label_ko` | VARCHAR | 원천 화면명 |  | 연료비용 |
| `source_url` | VARCHAR | 수집 엔드포인트 | URL | EPSIS AJAX endpoint |
| `frequency` | VARCHAR | 주기 |  | monthly |
| `disclosure_lag_rule` | VARCHAR | 공개 지연 규칙 |  | `monthly_m_plus_1_end_conservative` |
| `retrieved_at_utc` | VARCHAR | 수집 시각 | UTC | ISO-8601 문자열 |

---

## 30. EPSIS_POWER_TRADE_VOLUME_MONTHLY (월별 전력거래량)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `epsis_power_trade_volume_monthly` |
| **기간** | 2015-01-01 ~ 2025-12-01 |
| **행 수** | 132 행 |
| **컬럼 수** | 31 |
| **출처** | EPSIS/KPX 전력거래량 연료원별 |
| **파일** | `data/processed/features/epsis_power_trade_volume_monthly.parquet` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `feature_date` | DATE | 월 관측 기준일 | YYYY-MM-DD | 해당 월 1일 |
| `feature_month` | DATE | 관측 월 | YYYY-MM-DD | 월별 key |
| `asof_date` | DATE | 모델 사용 가능일 | YYYY-MM-DD | M+1 월말 보수적 공개 지연 적용 |
| `Period` | VARCHAR | 원천 기간 문자열 | YYYY/MM | EPSIS 원 컬럼명 유지 |
| `region` | VARCHAR | 지역 |  | 원천 응답 지역 구분, 현재 합계 |
| `trade_volume_nuclear_gwh` | NUMERIC | 원자력 전력거래량 | GWh |  |
| `trade_volume_bituminous_coal_gwh` | NUMERIC | 유연탄 전력거래량 | GWh |  |
| `trade_volume_anthracite_gwh` | NUMERIC | 무연탄 전력거래량 | GWh |  |
| `trade_volume_coal_total_gwh` | NUMERIC | 석탄 합계 전력거래량 | GWh | 유연탄+무연탄 |
| `trade_volume_oil_gwh` | NUMERIC | 유류 전력거래량 | GWh |  |
| `trade_volume_lng_gwh` | NUMERIC | LNG 전력거래량 | GWh |  |
| `trade_volume_pumped_storage_gwh` | NUMERIC | 양수 전력거래량 | GWh |  |
| `trade_volume_other_gwh` | NUMERIC | 기타 전력거래량 | GWh |  |
| `trade_volume_market_total_gwh` | NUMERIC | 전력시장 합계 거래량 | GWh |  |
| `trade_volume_ppa_total_gwh` | NUMERIC | PPA 합계 거래량 | GWh | 60 행 결측 |
| `trade_volume_market_ppa_total_gwh` | NUMERIC | 전력시장+PPA 합계 거래량 | GWh |  |
| `trade_volume_fuel_cell_gwh` | NUMERIC | 연료전지 전력거래량 | GWh |  |
| `trade_volume_coal_gasification_gwh` | NUMERIC | 석탄가스화 전력거래량 | GWh |  |
| `trade_volume_solar_gwh` | NUMERIC | 태양광 전력거래량 | GWh |  |
| `trade_volume_wind_gwh` | NUMERIC | 풍력 전력거래량 | GWh |  |
| `trade_volume_hydro_gwh` | NUMERIC | 수력 전력거래량 | GWh |  |
| `trade_volume_ocean_gwh` | NUMERIC | 해양 전력거래량 | GWh |  |
| `trade_volume_bio_gwh` | NUMERIC | 바이오 전력거래량 | GWh |  |
| `trade_volume_waste_gwh` | NUMERIC | 폐기물 전력거래량 | GWh |  |
| `trade_volume_renewable_total_gwh` | NUMERIC | 신재생 합계 전력거래량 | GWh | 연료전지·석탄가스화·태양광·풍력·수력·해양·바이오·폐기물 합계 |
| `source` | VARCHAR | 자료 출처 |  | `EPSIS/KPX` |
| `source_label_ko` | VARCHAR | 원천 화면명 |  | 전력거래량 연료원별 |
| `source_url` | VARCHAR | 수집 엔드포인트 | URL | EPSIS AJAX endpoint |
| `frequency` | VARCHAR | 주기 |  | monthly |
| `disclosure_lag_rule` | VARCHAR | 공개 지연 규칙 |  | `monthly_m_plus_1_end_conservative` |
| `retrieved_at_utc` | VARCHAR | 수집 시각 | UTC | ISO-8601 문자열 |

---

## 31. KMA_ASOS_WEATHER_STATION_DAILY (station-level 일별 기상)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `kma_asos_weather_station_daily` |
| **기간** | 2015-01-01 ~ 2025-12-31 |
| **행 수** | 24,108 행 |
| **컬럼 수** | 18 |
| **출처** | data.go.kr 기상청 ASOS 일자료 |
| **파일** | `data/processed/features/kma_asos_weather_station_daily.parquet` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `feature_date` | DATE | 관측 기준일 | YYYY-MM-DD | ASOS 일자료 기준일 |
| `asof_date` | DATE | 모델 사용 가능일 | YYYY-MM-DD | 일별 T+1 10시 보수적 공개 지연 적용 |
| `station_id` | VARCHAR | ASOS 지점 ID |  | 108, 133, 143, 156, 159, 184 |
| `station_name_ko` | VARCHAR | 지점명 |  | 서울, 대전, 대구, 광주, 부산, 제주 |
| `station_name_en` | VARCHAR | 지점 영문명 |  | Seoul, Daejeon, Daegu, Gwangju, Busan, Jeju |
| `avg_temp_c` | NUMERIC | 평균기온 | °C |  |
| `min_temp_c` | NUMERIC | 최저기온 | °C | 2 행 결측 |
| `max_temp_c` | NUMERIC | 최고기온 | °C | 2 행 결측 |
| `precip_mm` | NUMERIC | 일강수량 | mm | 무강수 공백은 0 처리 |
| `avg_wind_speed_mps` | NUMERIC | 평균풍속 | m/s | 23 행 결측 |
| `avg_relative_humidity_pct` | NUMERIC | 평균상대습도 | % | 4 행 결측 |
| `sunshine_hours` | NUMERIC | 일조시간 | hour | 88 행 결측 |
| `solar_radiation_mj_m2` | NUMERIC | 일사량 | MJ/m² | 162 행 결측 |
| `hdd18` | NUMERIC | 난방도일 | °C-day | `max(18 - avg_temp_c, 0)` |
| `cdd18` | NUMERIC | 냉방도일 | °C-day | `max(avg_temp_c - 18, 0)` |
| `is_precip_day` | INTEGER | 강수일 여부 | 0/1 | `precip_mm > 0` |
| `source` | VARCHAR | 자료 출처 |  | data.go.kr ASOS 일자료 서비스 |
| `retrieved_at` | VARCHAR | 수집 시각 | UTC | ISO-8601 문자열 |

---

## 32. KMA_ASOS_WEATHER_DAILY (aggregate 일별 기상)

### 기본 정보

| 항목 | 값 |
| --- | --- |
| **테이블명** | `kma_asos_weather_daily` |
| **기간** | 2015-01-01 ~ 2025-12-31 |
| **행 수** | 4,018 행 |
| **컬럼 수** | 17 |
| **출처** | data.go.kr 기상청 ASOS 일자료 |
| **파일** | `data/processed/features/kma_asos_weather_daily.parquet` |

### 컬럼 목록

| 컬럼명 | 타입 | 설명 | 단위 | 비고 |
| --- | --- | --- | --- | --- |
| `feature_date` | DATE | 관측 기준일 | YYYY-MM-DD | ASOS 일자료 기준일 |
| `asof_date` | DATE | 모델 사용 가능일 | YYYY-MM-DD | 일별 T+1 10시 보수적 공개 지연 적용 |
| `station_count` | INTEGER | 집계 지점 수 | 개 | 고정 basket 6개 지점 |
| `station_basket` | VARCHAR | 집계 지점 ID 목록 |  | `108,133,143,156,159,184` |
| `aggregation_method` | VARCHAR | 집계 방식 |  | `simple_average_across_station_basket` |
| `avg_temp_c` | NUMERIC | 평균기온 단순평균 | °C | 6개 지점 평균 |
| `min_temp_c` | NUMERIC | 최저기온 단순평균 | °C | 6개 지점 평균 |
| `max_temp_c` | NUMERIC | 최고기온 단순평균 | °C | 6개 지점 평균 |
| `precip_mm` | NUMERIC | 일강수량 단순평균 | mm | 6개 지점 평균 |
| `avg_wind_speed_mps` | NUMERIC | 평균풍속 단순평균 | m/s | 6개 지점 평균 |
| `avg_relative_humidity_pct` | NUMERIC | 평균상대습도 단순평균 | % | 6개 지점 평균 |
| `sunshine_hours` | NUMERIC | 일조시간 단순평균 | hour | 6개 지점 평균 |
| `solar_radiation_mj_m2` | NUMERIC | 일사량 단순평균 | MJ/m² | 6개 지점 평균 |
| `hdd18` | NUMERIC | 난방도일 단순평균 | °C-day | 6개 지점 평균 |
| `cdd18` | NUMERIC | 냉방도일 단순평균 | °C-day | 6개 지점 평균 |
| `is_precip_day` | NUMERIC | 강수일 지점 비율 | 0~1 | station-level 0/1 값을 평균 |
| `retrieved_at` | VARCHAR | 수집 시각 | UTC | ISO-8601 문자열 |