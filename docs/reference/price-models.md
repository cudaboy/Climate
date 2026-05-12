# 탄소배출권 가격 결정 모형 및 예측 모델 개발을 위한 통합 선행연구 분석 보고서

## 서론

전 지구적 기후 위기에 대응하기 위한 탄소 중립 목표가 법제화됨에 따라 탄소배출권 거래제(Emissions Trading System, ETS)는 가장 비용 효율적인 온실가스 감축 수단으로 자리 잡았다.[1, 2] 탄소배출권 가격은 단순한 시장 지표를 넘어 기업의 저감 기술 투자 여부와 국가 경제의 탄소 집약도를 결정하는 핵심적인 신호 기제로 작동한다.[3, 4] 특히 유럽 연합 탄소배출권 거래제(EU-ETS)와 한국 탄소배출권 거래제(K-ETS)는 각각 시장 성숙도와 제도적 특성 면에서 뚜렷한 차이를 보이며 발전해 왔으며, 이러한 차이는 가격 결정 모형의 설계에 있어 서로 다른 변수 선택과 방법론적 접근을 요구한다.[5, 6]

본 연구 보고서는 배출권 가격 결정 모형 및 예측 모델 개발을 위한 체계적인 선행 연구 분석을 제공한다. 특히 타겟 변수로서의 거래량 가중평균가격(VWAP) 및 빈티지(Vintage) 결정 로직, 그리고 통계적 유의성을 확보하기 위한 피처(Feature) 선택 기준인 LASSO 및 Granger 인과관계 검정 등의 방법론을 심도 있게 고찰하며, 10,000자 이상의 상세한 분석을 통해 전문가적 통찰을 제시한다.

---

## 탄소배출권 시장의 구조적 메커니즘과 제도적 진화

탄소배출권 가격 예측 모델을 설계하기에 앞서 각 시장의 구조적 특징과 가격 형성의 제도적 배경을 이해하는 것은 필수적이다. EU-ETS와 K-ETS는 시장의 성숙도와 유동성, 그리고 정책적 개입의 빈도에서 큰 차이를 보인다.[2, 7]

### 글로벌 탄소배출권 시장의 단계별 발전과 정책적 동인

유럽 연합은 2005년 세계 최초의 대규모 탄소 시장인 EU-ETS를 출범시킨 이후 현재 4기(2021-2030) 운영 단계에 진입해 있다.[8, 9] EU-ETS의 가격 결정은 초기에는 단순히 할당량의 희소성에 의존했으나, 2018년 시장안정화예비분(Market Stability Reserve, MSR)의 도입으로 공급 과잉 문제를 해결하며 가격의 하방 경직성을 확보했다.[2] 최근에는 'Fit for 55' 패키지를 통해 선형 감축 계수(LRF)를 2024년 4.3%, 2028년 4.4%로 상향 조정하며 공급을 기계적으로 축소하고 있다.[10]

대한민국의 K-ETS는 2015년 동아시아 최초로 국가 단위 강제적 시장으로 도입되었으며, 2023년 기준으로 국가 전체 배출량의 약 77.8%를 점유하고 있다.[7, 11] K-ETS는 도입 초기 유동성 부족과 시장 참여자들의 정보 비대칭성으로 인해 가격이 펀더멘털보다 제도적 변경이나 이월 제한 조치에 더 민감하게 반응하는 양상을 보였다.[5, 12] 특히 2026년부터 시작되는 4기 계획에서는 유상 할당 비중의 확대와 수량 기반 시장 안정화 장치(K-MSR)의 고도화가 예정되어 있어, 가격 결정 모형에 이러한 제도적 변화를 반영하는 것이 더욱 중요해졌다.[7]

| 주요 비교 항목 | EU-ETS (유럽 연합) | K-ETS (대한민국) |
|---|---|---|
| 법적 근거 및 목표 | EU 지침, 2030년까지 1990년 대비 55% 감축 | 탄소중립기본법, 2030년까지 2018년 대비 40% 감축 |
| 시장 성숙도 및 유동성 | 매우 높음 (선물 및 파생상품 중심) | 보통 (장내 현물 거래 비중이 높으나 유동성 부족 존재) |
| 가격 안정화 기제 | MSR (공급량 자동 조절) | 정부 시장 안정화 조치 (최저가격, 추가할당 등) |
| 주요 업종 및 범위 | 발전, 항공, 에너지 집약 산업, 해운(2024년 추가) | 발전, 산업, 건물, 폐기물, 수송, 공공 등 광범위함 |
| 가격 결정 핵심 변수 | 가스/석탄 가격차(Fuel Switching), 규제 업데이트 | 할당량, 이월 제한 규정, 국내 경기 지표 |

[2, 7, 8, 11]

## 타겟 변수 엔지니어링: VWAP와 빈티지 결정 모델

예측 모델의 성능은 예측 대상이 되는 타겟 변수(Target Variable)를 어떻게 정의하느냐에 따라 결정적인 차이를 만든다. 전통적인 금융 모델링에서는 일일 종가(Closing Price)를 주로 사용하지만, 탄소배출권 시장과 같이 거래 빈도가 불규칙하거나 특정 시점에 거래가 집중되는 환경에서는 보다 정교한 지표가 요구된다.[13]

### 거래량 가중평균가격(VWAP)의 금융 공학적 우위성

VWAP(Volume-Weighted Average Price)는 특정 거래 기간 동안 발생한 모든 거래의 가격을 해당 거래량으로 가중 평균하여 산출한 지표이다. 배출권 가격 예측 모델에서 VWAP를 타겟 변수로 선택해야 하는 논리적 근거는 다음과 같다.[13, 14]

첫째, 시장 충격 비용(Market Impact Costs)의 상쇄이다. 배출권 시장, 특히 K-ETS와 같이 유동성이 낮은 시장에서는 단일 대량 거래가 종가를 왜곡시킬 위험이 크다. VWAP는 장중 모든 거래를 통합하므로 일시적인 가격 튐(Outliers) 현상을 완화하고 해당 거래일의 실질적인 가치 수준을 반영한다.[13] 둘째, 기관 투자자의 실행 가능성(Executability)이다. 배출권을 대량으로 확보해야 하는 규제 대상 업체는 특정 시점의 종가로 물량을 확보하기보다는 일정 시간 동안 분할 매수하여 VWAP 수준의 평균 단가를 맞추는 전략을 취한다.[14, 15] 따라서 예측 모델이 VWAP를 타겟으로 할 때 실제 트레이딩 전략과의 정합성이 높아진다.[13]

셋째, 정보 효율성의 증대이다. 선행 연구에 따르면 VWAP는 종가보다 시장의 펀더멘털 정보를 더 밀도 있게 포함하고 있으며, 특히 장 마감 직전의 심리적 요인이나 유동성 노이즈를 제거하는 효과가 있다.[13, 16] VWAP를 활용한 모델링 시에는 타임 윈도우 설정이 중요한데, 일반적으로 60분 단위의 비중첩 구간(Non-overlapping Window)을 설정하여 장 시작과 장 종료 시점의 가격 동학을 분리 학습하는 방식이 권장된다.[13]

### 빈티지(Vintage)의 정의 및 가격 차별화 요인

탄소배출권에서 빈티지는 해당 배출권이 생성된 연도나 해당되는 이행 연도를 지칭한다. 빈티지는 단순한 시간 정보가 아니라 배출권의 가치와 법적 효력을 결정하는 핵심 속성이다.[17, 18]

예측 모델 개발 시 빈티지 데이터를 처리하는 핵심 기준은 다음과 같다. 우선, 자발적 탄소 시장(VCM)의 관점에서 빈티지는 품질의 대리 변수(Proxy)로 작동한다. 최신 빈티지(예: 2021-2023)는 과거 빈티지(예: 2016-2020)에 비해 약 217%의 가격 프리미엄을 형성하는 것으로 보고되었다.[17] 이는 최신 방법론이 적용되었으며, 기업의 탄소 발자국 보고 시점과 일치하는 배출권을 선호하는 시장의 수요를 반영한다.[17, 19]

반면 규제 시장인 K-ETS나 EU-ETS에서 빈티지(KAU15, KAU16 등)는 이월 및 차입 규정과 직접적으로 연결된다. K-ETS 초기 단계에서는 특정 빈티지의 이행 기간 종료 시점에 매도세가 집중되거나 정부의 이월 제한 조치로 인해 가격이 급락하는 빈티지별 특이 현상이 관찰되었다.[5, 12] 따라서 예측 모델링 시 빈티지는 범주형 변수(Categorical Variable)로 인코딩되거나, 이행 연도별 수급 불균형을 반영할 수 있는 시계열 더미 변수로 처리되어야 한다.[17, 20]

## 탄소배출권 가격 결정 요인 및 피처 선택 메커니즘

배출권 가격은 에너지 시장, 거시경제, 기상 요인, 정책적 변수들이 복잡하게 얽힌 다변량 시스템에 의해 결정된다.[4, 21] 예측 모델의 설명력과 정밀도를 높이기 위해서는 수많은 후보 피처들 중에서 정보량이 가장 높은 변수를 추출하는 과정이 필수적이다.[3, 22]

### 주요 영향 요인별 계량경제적 분석

배출권 가격에 영향을 미치는 핵심 피처 그룹은 크게 네 가지로 분류되며, 각 변수의 영향력은 시장의 성숙도에 따라 상이하게 나타난다.[3, 5, 21]

- **에너지 가격 지표:** 천연가스, 석탄, 브렌트유 가격은 발전 부문의 연료 전환 비용을 결정한다. 특히 가스 가격 상승 시 석탄 발전 비중이 높아지며 탄소 배출량이 증가하고, 이는 배출권 수요 확대로 이어져 가격을 상승시킨다.[2, 10]
- **거시경제 및 산업 지표:** GDP 성장률, 산업 생산 지수, 유로스톡스 50(Euro Stoxx 50)이나 코스피(KOSPI) 같은 주식 지수는 탄소 집약적 산업의 가동률과 정(+)의 상관관계를 갖는다.[5, 21]
- **기상 및 환경 변수:** 기온(Heating/Cooling Degree Days), 강수량, 풍속 등은 난방 및 냉방 수요를 통한 전력 소비량과 수력·풍력 발전의 공급량에 영향을 미쳐 배출권 수요의 변동성을 키운다.[5, 10]
- **기술적 및 시장 심리 지표:** 이동평균선(SMA), 상대강도지수(RSI) 등의 기술적 지표와 더불어 최근 연구에서는 네이버나 구글의 검색 트렌드 데이터를 활용하여 시장 참여자의 불안이나 관심을 수치화하여 모델에 반영한다.[3, 23, 24]

### 피처 선택을 위한 통계적 방법론: LASSO와 Granger 인과성

고차원 데이터셋에서 유의미한 변수를 선별하기 위해 LASSO(Least Absolute Shrinkage and Selection Operator) 회귀 모델이 표준적으로 사용된다.[25, 26, 27] LASSO는 회귀 계수의 절대값 합에 비례하는 패널티를 부여하여 중요도가 낮은 피처의 계수를 정확히 0으로 수렴시킴으로써 모델의 복잡도를 줄이고 해석력을 높인다.[27, 28]

$$\hat{\beta}_{\text{LASSO}} = \arg\min_{\beta} \left( \sum_{i=1}^{n} \left( y_i - \sum_{j=1}^{p} x_{ij} \beta_j \right)^2 + \lambda \sum_{j=1}^{p} |\beta_j| \right)$$

또한 Granger 인과관계 검정은 특정 피처의 과거 정보가 타겟 변수인 배출권 가격의 예측력을 통계적으로 유의하게 개선하는지 확인하는 데 활용된다.[21, 27] 특히 K-ETS와 같이 제도적 변화가 잦은 시장에서는 정책 변수나 에너지 가격의 시차(Lag) 효과를 파악하기 위해 Granger 검정이 변수 선택의 핵심 기준으로 작용한다.[5, 25]

### SHAP 가치 분석을 통한 모델 해석력 확보

머신러닝 모델의 '블랙박스' 문제를 해결하기 위해 SHAP(Shapley Additive Explanations) 분석이 도입되고 있다.[4] SHAP 가치는 게임 이론에 기초하여 각 피처가 예측 결과에 기여한 정도를 공정하게 배분한다. 이를 통해 특정 시점의 배출권 가격 급등이 가스 가격 상승 때문인지, 아니면 기온 저하에 따른 수요 폭증 때문인지 정량적으로 설명할 수 있게 된다.[4] 이는 모델의 신뢰성을 높여줄 뿐만 아니라 정책 결정자가 시장 안정화 조치를 실행할 수 있는 과학적 근거를 제공한다.[4]

## 배출권 가격 예측 모델의 구조와 알고리즘 진화

예측 모델의 구조는 초기 선형 통계 모델에서 시작하여 현재는 딥러닝과 데이터 분해 기술이 결합된 하이브리드 형태로 진화했다.[29, 30]

### 전통적 통계 모델과 머신러닝의 결합

초기 선행 연구들은 ARIMA나 GARCH 모델을 통해 배출권 가격의 자기상관성과 변동성 밀집 현상을 분석했다.[24, 31, 32] 그러나 배출권 가격의 비선형적이고 비정상적인(Non-stationary) 특성으로 인해 단일 통계 모델의 정확도는 한계를 보였다.[4, 27] 이를 보완하기 위해 XGBoost, Random Forest, SVM 등의 머신러닝 알고리즘이 도입되었으며, 이들은 다변량 데이터 간의 복잡한 비선형 관계를 학습하는 데 우수한 성능을 나타낸다.[4, 33]

### 딥러닝 기반의 시퀀스 모델링 (LSTM, GRU, Transformer)

시간에 따른 장기 의존성을 포착하기 위해 RNN의 변형 모델인 LSTM(Long Short-Term Memory)과 GRU(Gated Recurrent Unit)가 널리 채택된다.[3, 27, 31] 특히 GRU는 LSTM보다 구조가 단순하면서도 데이터가 상대적으로 적은 배출권 시장에서 안정적인 학습 성능을 보인다.[4]

최근에는 어텐션 메커니즘(Attention Mechanism)을 활용한 Transformer 기반 모델이 시계열 예측의 새로운 지평을 열고 있다.[4, 31] 어텐션 메커니즘은 전체 시계열 중 가격 변동의 핵심적인 '이벤트 시점'에 더 많은 가중치를 두어 학습함으로써, 정책 발표나 경제적 충격 상황에서의 예측 정확도를 획기적으로 높인다.[4, 22]

| 모델 유형 | 주요 방법론 | 장점 | 적용 사례 및 결과 (MAPE) |
|---|---|---|---|
| 통계 모델 | ARIMA, GARCH | 선형 패턴 파악, 모델 해석 용이 | 벤치마크 모델로 주로 활용 |
| 머신러닝 | XGBoost, RF, SVM | 비선형 관계 학습, 고차원 피처 처리 | Hubei 시장 RMSE 99.9% 개선 [27] |
| 딥러닝 | LSTM, BiGRU | 장기 의존성 포착, 연속적 흐름 학습 | 후베이 시장 MAPE 0.8125% [29] |
| 하이브리드 | CEEMDAN-WOA-GRU | 데이터 노이즈 제거 및 최적화 결합 | 유럽/중국 시장 MAPE 0.4~1.0% [4] |

[4, 27, 29, 31]

## 고도화된 데이터 전처리: 신호 분해 기술 (CEEMDAN, VMD)

배출권 가격 데이터는 시장 노이즈가 많고 변동성이 매우 크기 때문에, 원 데이터를 여러 성분으로 분해하여 예측하는 방식이 주류 방법론으로 자리 잡았다.[30, 34]

### 분해-예측-결합(Decomposition-Ensemble) 프레임워크

CEEMDAN(Complete Ensemble Empirical Mode Decomposition with Adaptive Noise)은 복잡한 가격 신호를 여러 개의 IMF(Intrinsic Mode Functions)와 하나의 잔차(Residual)로 분해한다.[34, 35] 각 IMF는 고주파(단기 변동), 중주파(주기성), 저주파(장기 추세) 특성을 갖는다.[30] 이후 가장 복잡한 고주파 성분에 VMD(Variational Mode Decomposition)를 추가 적용하는 2차 분해 기술은 데이터의 불규칙성을 극도로 낮추어 예측 모델의 학습 부담을 덜어준다.[22, 34, 36]

분해된 각 성분은 Lempel-Ziv 알고리즘이나 샘플 엔트로피(Sample Entropy) 분석을 통해 복잡도가 측정되며, 각 성분의 특성에 맞는 서로 다른 모델(예: 고주파는 딥러닝, 저주파는 선형 모델)을 적용하여 개별 예측한 뒤 이를 최종 합산함으로써 전체 예측 오차를 최소화한다.[30, 35, 36]

## K-ETS 시장의 특수성과 모델링 실무 가이드

한국 탄소 시장은 유동성 부족과 정책적 개입이라는 고유한 특성을 가지고 있어, 일반적인 금융 예측 모델을 그대로 적용할 경우 한계가 명확하다.[1, 12]

### 유동성 부족과 '기세' 가격의 처리 전략

K-ETS에서는 거래가 전혀 발생하지 않는 날이 빈번하며, 이때 거래소는 매도·매수 호가의 중간값을 바탕으로 '기세(Gise)' 가격을 산출한다.[5] 기세 가격은 실제 수급이 반영되지 않은 명목적 가격일 수 있으므로, 모델 학습 시 거래량이 0인 구간에 대해서는 가중치를 낮추거나 VWAP를 활용하여 데이터의 신뢰도를 보정해야 한다.[5, 13] 또한 유동성을 인위적으로 공급하는 시장 조성자(Market Maker)의 활동 기간을 더미 변수로 반영하는 것도 필요하다.[7]

### 정책 변수의 정량화 및 시나리오 기반 예측

정부의 이월 제한 조치, 할당 취소, 시장 안정화 물량 공급 등은 시장의 펀더멘털을 일시에 바꾸는 구조적 변화 요인이다.[1] K-ETS 4기에서는 수량 기반의 MSR이 도입될 예정이므로, MSR 작동 임계치(Threshold)에 근접한 정도를 피처로 생성하여 모델에 입력하는 것이 중요하다.[1, 7] 또한 규제 환경의 불확실성을 반영하기 위해 단일 예측치보다는 확률적 구간 예측(Interval Forecasting)을 수행하여 리스크의 범위를 제시하는 것이 바람직하다.[29]

## 결론 및 모델 개발 제언

본 연구 보고서를 통해 분석한 배출권 가격 결정 모형의 핵심 성공 요인은 타겟 변수의 정교화, 체계적인 피처 선택, 그리고 데이터 분해 기술을 활용한 하이브리드 알고리즘의 적용으로 요약된다.

예측 모델의 타겟은 시장 실무와 정합성이 높은 VWAP를 우선적으로 고려해야 하며, 빈티지 데이터를 통해 배출권의 품질 및 이행 주기별 특성을 반영해야 한다. 피처 선택 단계에서는 LASSO와 Granger 인과성 검정을 통해 정보 노이즈를 제거하고, 에너지 가격과 정책적 이벤트를 통합한 다차원 변수 세트를 구축해야 한다. 모델 구조는 CEEMDAN-VMD 분해 기술과 Transformer-GRU와 같은 최첨단 딥러닝 아키텍처를 결합함으로써 비선형적 변동성을 포착하는 능력을 극대화해야 한다.

특히 국내 K-ETS 환경에서는 유동성 부족에 따른 가격 왜곡 현상을 기술적으로 보정하고, 4기 계획에서 강화되는 시장 안정화 기제와 유상 할당 비중의 변화를 선제적으로 모델에 내재화하는 노력이 요구된다. 이러한 통합적 접근은 배출권 시장 참여자에게는 효율적인 자산 관리 도구를 제공하고, 정책 입안자에게는 안정적인 시장 운영을 위한 과학적 이정표를 제시할 것이다.

---

## 참고 문헌

1. Approaches to Enhance the Market Functionality of the K-ETS - KDI - Korea Development Institute - RESEARCH, https://www.kdi.re.kr/eng/research/focusView?pub_no=18054
2. Trends in carbon intensity and the macroeconomic role of the EU Emissions Trading System, https://economy-finance.ec.europa.eu/trends-carbon-intensity-and-macroeconomic-role-eu-emissions-trading-system_en
3. Carbon price prediction based on a scaled PCA approach - PMC - NIH, https://pmc.ncbi.nlm.nih.gov/articles/PMC10760667/
4. Carbon Price Prediction Based on Comprehensive Feature Selection and WOA-Driven MultiHead-Attention-BiGRU Model - ResearchGate, https://www.researchgate.net/publication/400354001_Carbon_Price_Prediction_Based_on_Comprehensive_Feature_Selection_and_WOA-Driven_MultiHead-Attention-BiGRU_Model
5. 한국 탄소배출권시장 가격결정체계의 학습효과 ... - 자원 · 환경경제연구, https://journal.resourceeconomics.or.kr/articles/pdf/oj4R/erer-2018-027-04-3.pdf
6. Emerging Markets' Carbon Pricing Development: A Comparative Analysis of China and South Korea's Experience - MDPI, https://www.mdpi.com/2673-4060/6/2/58
7. Korea Emissions Trading System (K-ETS) - International Carbon Action Partnership (ICAP), https://icapcarbonaction.com/en/ets/korea-emissions-trading-system-k-ets
8. Compare ETS | International Carbon Action Partnership, https://icapcarbonaction.com/en/compare/55/43/47
9. PRICE DISCOVERY IN CARBON MARKETS: EVIDENCE FROM PHASE III & IV OF EU-ETS, https://ubplj.org/index.php/jpm/article/download/2242/2111/8844
10. EUA Carbon Price in 2026: Forecasts and Scenarios Through 2030 | Homaio, https://www.homaio.com/post/2030-eua-price-predictions-expert-analysis-of-3-scenarios
11. Compare ETS | International Carbon Action Partnership, https://icapcarbonaction.com/en/compare/47/59/119
12. Full article: Efficiency in the Early Stages of Carbon Markets: The Case of the Korean Emissions Trading Scheme - Taylor & Francis, https://www.tandfonline.com/doi/full/10.1080/1540496X.2024.2379460
13. Machine Learning in Futures Markets - MDPI, https://www.mdpi.com/1911-8074/14/3/119
14. Optimal Execution Strategies - UWSpace - University of Waterloo, https://www.uwspace.uwaterloo.ca/bitstreams/9999aefb-84b4-414e-9e95-8b9a51a4cb29/download
15. Using a Genetic Algorithm to Build a Volume Weighted Average Price Model in a Stock Market - MDPI, https://www.mdpi.com/2071-1050/13/3/1011
16. Opening and Closing Price Efficiency: Do Financial Markets need the Call Auction? | Request PDF - ResearchGate, https://www.researchgate.net/publication/262297941_Opening_and_Closing_Price_Efficiency_Do_Financial_Markets_need_the_Call_Auction
17. Carbon Credit Vintage: Study on Valuation Impact - Phoenix ..., https://www.phoenixstrategy.group/blog/carbon-credit-vintage-valuation-impact
18. More than just the year on the label: Understanding the value of carbon credit vintages, https://www.ceezer.earth/insights/beyond-the-year-on-the-label-understanding-the-value-of-carbon-credit-vintages
19. Carbon Offset Pricing Trends: What Buyers Should Budget for in 2026 - Sylvera, https://www.sylvera.com/blog/carbon-offset-price
20. Market-based instruments, technological innovation, and enterprise air pollution: evidence from China's carbon emissions trading system - Frontiers, https://www.frontiersin.org/journals/environmental-science/articles/10.3389/fenvs.2026.1760666/full
21. Perception and Prediction of Factors Influencing Carbon Price: Multisource, Spatiotemporal, Hierarchical Federated Learning Framework with Cross-Modal Feature Fusion - PMC, https://pmc.ncbi.nlm.nih.gov/articles/PMC12693995/
22. Research on forward multi-step prediction of EU carbon prices ..., https://pmc.ncbi.nlm.nih.gov/articles/PMC12140658/
23. Performance Comparison of Predictive Methodologies for Carbon ..., https://www.mdpi.com/2071-1050/14/13/8177
24. Performance Comparison of Predictive Methodologies for Carbon Emission Credit Price in the Korea Emission Trading System - ResearchGate, https://www.researchgate.net/publication/361776922_Performance_Comparison_of_Predictive_Methodologies_for_Carbon_Emission_Credit_Price_in_the_Korea_Emission_Trading_System
25. Feature Selection for Rare Earth Element Price Forecasting - Lund University Publications, https://lup.lub.lu.se/student-papers/record/9202593/file/9202611.pdf
26. Carbon Price Combination Forecasting Model Based on Lasso Regression and Optimal Integration - MDPI, https://www.mdpi.com/2071-1050/15/12/9354
27. Dynamic prediction of carbon prices based on the multi-frequency combined model - PMC, https://pmc.ncbi.nlm.nih.gov/articles/PMC12190694/
28. Apply lasso regression to automate feature selection - IBM Developer, https://developer.ibm.com/tutorials/awb-lasso-regression-automatic-feature-selection/
29. Carbon Price Point and Interval-Valued Prediction Based on a Novel Hybrid Model - MDPI, https://www.mdpi.com/1996-1073/18/5/1054
30. A Decomposition-Integration Framework of Carbon Price Forecasting Based on Econometrics and Machine Learning Methods - MDPI, https://www.mdpi.com/2227-7390/13/3/464
31. Carbon Price Forecasting for Sustainable Low-Carbon Investment ..., https://www.mdpi.com/2071-1050/18/5/2324
32. Carbon Prices Forecasting Using Group Information - Energy RESEARCH LETTERS, https://erl.scholasticahq.com/article/36615-carbon-prices-forecasting-using-group-information
33. A Hybrid Methodology Using Machine Learning Techniques and Feature Engineering Applied to Time Series for Medium- and Long-Term Energy Market Price Forecasting - MDPI, https://www.mdpi.com/1996-1073/18/6/1387
34. Forecasting Carbon Price with Secondary Decomposition Algorithm and Optimized Extreme Learning Machine - MDPI, https://www.mdpi.com/2071-1050/13/15/8413
35. Carbon price prediction based on multiple decomposition and XGBoost algorithm, https://www.researchgate.net/publication/370799810_Carbon_price_prediction_based_on_multiple_decomposition_and_XGBoost_algorithm
36. Carbon price prediction based on multiple decomposition and XGBoost algorithm - OUCI, https://ouci.dntb.gov.ua/en/works/lmkpRGm7/
