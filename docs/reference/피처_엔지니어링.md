# 탄소배출권 가격 결정 및 고도화된 예측 피처 엔지니어링을 위한 종합 분석 프레임워크

## 서론

이 보고서는 탄소배출권 가격 결정의 복잡한 구조를 분석하고 예측 정확도를 높이기 위한 고도화된 피처 엔지니어링 프레임워크를 제시한다. 탄소배출권은 더 이상 단순한 규제 수단이 아니라 에너지 시장, 거시 경제, 기상 조건 및 정부의 정책적 개입과 밀접하게 연결된 정교한 금융 자산으로 정의된다. 특히 전력 생산 비용의 수익성을 나타내는 스파크·다크 스프레드와 같은 파생 변수와 뉴스 심리를 분석한 비정형 데이터를 결합하여 시장의 비선형적 변동성을 파악하는 것이 핵심이다. 궁극적으로 이 텍스트는 한국 탄소배출권 거래제 (K-ETS) 의 성숙도에 따른 시장 변화를 설명하며, 투자자와 정책 입안자가 미래의 공급 희소성에 효과적으로 대응할 수 있는 다차원적인 예측 모델 구축을 제안한다.

---

## 탄소배출권 가격 결정 및 고도화된 예측 피처 엔지니어링을 위한 종합 분석 프레임워크

저탄소 경제로의 글로벌 전환은 탄소배출권의 역할을 근본적으로 재정의하였으며, 단순한 규제 수단에서 높은 변동성과 글로벌 에너지·거시경제 시스템과의 비선형적 상호의존성을 특징으로 하는 복잡한 금융 자산으로 변모시켰다.[1, 2] 유럽연합 배출권거래제 (EU ETS) 와 한국 배출권거래제 (K-ETS) 가 성숙해짐에 따라, 기관 투자자, 산업계 의무이행 주체, 그리고 정책 입안자에게 정교한 가격 결정 모델과 예측 프레임워크의 필요성은 더욱 절대적인 과제가 되었다.[3, 4, 5] 이러한 배출권의 가치 평가는 경제 활동, 에너지 상품 가격, 기상 패턴, 그리고 고빈도 (high-frequency) 정책 충격을 망라하는 복잡한 요인들의 그물망에 의해 영향을 받으며, 예측 정확성을 보장하기 위해 모든 요인은 세심한 피처 엔지니어링과 파생 변수 (derived variables) 의 개발을 요구한다.[3, 6]

## 탄소 시장 동학 및 가격 형성의 이론적 토대

탄소 가격의 결정은 정부의 캡 (cap) 에 의해 행정적으로 고정된 배출권 공급과, 산업 활동 및 전력 생산에 의해 발생하는 수요 사이의 근본적인 균형에 뿌리를 두고 있다.[2, 7] 공급이 가격 신호에 반응하여 생산이나 채굴 증가를 통해 조절될 수 있는 전통적인 상품과는 달리, 탄소배출권의 공급은 다년도 할당 계획과 시장안정화예비분 (Market Stability Reserve, MSR) 과 같은 제도적 메커니즘에 의해 결정되어 단기적으로는 완전 비탄력적이다.[8, 9] 따라서 가격 변동은 주로 수요의 변화와 미래의 희소성에 대한 시장의 집단적 인식에 의해 견인된다.[7, 10]

K-ETS 의 맥락에서, 가격 결정 시스템은 연구자들이 "행함에 의한 학습 (learning-by-doing)" 효과라고 식별하는 과정을 통해 상당히 진화해왔다.[11] 초기 단계 (KAU15) 동안, 시장 참여자들은 주로 규제 준수에만 집중하였으며, 이로 인해 시장은 거시 경제 지표로부터 비교적 고립되어 있었고 행정적 마감일에만 반응적이었다.[11] 시장이 이후 단계 (KAU16 이후) 로 이동하면서, 탄소 가격 (한국 배출권, KAU) 과 금리, 환율, 주가지수 등 외부 변수 사이의 상관관계가 통계적으로 유의미해졌다.[11] 이는 시장의 성숙이 참여자들이 거래 행위에 복잡한 경제 신호를 반영하는 보다 "효율적인" 가격 메커니즘으로 이어진다는 점을 보여준다.[11, 12]

| 단계 / 시기 | 주요 가격 동인 | 외부 변수의 통계적 유의성 |
|---|---|---|
| KAU15 (2015–2016) | 시장 내부 요인, 제도적 마감일 | 낮음 [11] |
| KAU16 (2016–2017) | 거시 경제 지표, 시장 내부 요인 | 높음 [11] |
| K-ETS 3 기 (2021–2025) | 에너지 가격, 정책 충격, 경제성장 | 매우 높음 [12] |
| K-ETS 4 기 (2026–2030) | MSR 발동 요건, CBAM 통합, 유동성 조치 | 지배적 요인이 될 것으로 예측 [13] |

탄소 시장의 가격 발견 (price discovery) 역할은 현물 (spot) 시장과 선물 (futures) 시장 간의 상호작용에 의해 더욱 복잡해진다.[5] 탄소 선물은 이론적으로 가격 예측 기능을 보유하며 위험 헤지 수단으로 기능하지만, 지정학적 혼란이나 선형 감축 계수 (Linear Reduction Factor, LRF) 변경에 의해 촉발되는 투기적 거품 및 갑작스러운 체제 전환 (regime shift) 에 여전히 취약하다.[5, 14, 15] 따라서 어떤 예측 모델이라도 구조적 수요–공급 균형뿐만 아니라 시장 정서와 투기에 관련된 비구조적 요인까지 모두 고려해야 한다.[16]

## 에너지 시장 스프레드 및 연료 전환에서 도출된 파생 변수

전력 생산 부문은 탄소배출권의 가장 큰 소비처로서, 에너지 시장 동학을 단기 가격 변동에 가장 즉각적이고 영향력 있는 동인으로 만든다.[16, 17] 탄소 가격과 석탄, 천연가스, 전력 등의 에너지 상품 사이의 관계는 서로 다른 발전 기술의 상대적 수익성을 통해 매개되며, 이 개념은 "스프레드 (spread)"의 수학적 도출로 포착된다.[18, 19]

### 수익성 지표: 스파크 스프레드와 다크 스프레드

"스파크 스프레드 (spark spread)"와 "다크 스프레드 (dark spread)"는 각각 천연가스 화력발전소와 석탄 화력발전소의 총 마진을 나타낸다.[18, 20] 이 지표들이 탄소 배출 비용을 포함하도록 조정되면, 예측 모델에서 핵심적인 파생 변수로 기능하는 "클린 (clean) 스프레드"가 된다.[17, 21]

이 클린 스프레드들의 수학적 정식화는 다음과 같다.

**클린 스파크 스프레드 (Clean Spark Spread, CSS):**

$$\text{CSS} = P_{\text{elec}} - (P_{\text{gas}} \times HR_{\text{gas}}) - (P_{\text{carbon}} \times EF_{\text{gas}})$$

**클린 다크 스프레드 (Clean Dark Spread, CDS):**

$$\text{CDS} = P_{\text{elec}} - (P_{\text{coal}} \times HR_{\text{coal}}) - (P_{\text{carbon}} \times EF_{\text{coal}})$$

이들 식에서 $P$는 시장 가격, $HR$은 열효율 (heat rate; 1MWh 의 전력을 생산하는 데 필요한 연료량을 나타내는 에너지 효율 지표), $EF$는 생산된 에너지 단위당 배출 계수 (emission factor) 를 의미한다.[17, 19] 양 (+) 의 스프레드는 수익성을 의미하며, 음 (-) 의 스프레드는 발전소가 생산을 축소해야 할 수도 있음을 시사하는 신호이다.[18]

"연료 전환 가격 (switching price)"은 CDS 가 CSS 와 같아지는 시점의 탄소 가격으로 정의되는 2 차 파생 변수이다.[17] 이 임계치는 발전사업자가 석탄에서 천연가스로 전환할 경제적 유인을 갖게 되는 지점을 나타낸다.[17] 천연가스는 석탄보다 약 50% 가량 탄소 집약도가 낮기 때문에, 이 전환은 탄소배출권 수요의 급격한 감소로 이어지며 가격에 하방 압력을 행사한다.[17, 22] 반대로 가스 가격이 크게 상승하면, 연료 전환 가격이 상승하여 발전사업자가 다시 석탄으로 회귀하게 만들고 그에 따라 배출권 수요가 증가하게 된다.[17, 23]

| 스프레드 유형 | 계산 구성 요소 | 시장 신호의 함의 |
|---|---|---|
| 단순 스파크 스프레드 (Simple Spark Spread) | 전력 가격, 천연가스 가격, 열효율 | 가스 발전의 기본 수익성 [21] |
| 클린 스파크 스프레드 (Clean Spark Spread) | 전력 가격, 가스 가격, 탄소 가격, 배출 계수 | ETS 규제 하의 운영 가능성 [19, 21] |
| 클린 다크 스프레드 (Clean Dark Spread) | 전력 가격, 석탄 가격, 탄소 가격, 배출 계수 | 석탄의 경제적 가능성; 배출권 수요의 주된 동인 [17, 19] |
| 연료 전환 가격 (Fuel Switching Price) | CDS-CSS 등가점 | 탄소 가격의 저항/지지 수준 [17] |

연구 결과에 따르면, 석탄 가격은 장기적인 탄소 가격 추세에 가장 유의한 요인으로 작용하는 경우가 많은 반면, 천연가스 가격과 그에 연관된 변동성 지수 (예: Crude Oil Volatility Index, OVX) 는 단기 변동성에 대한 더 나은 예측 지표이다.[16, 24] 중국의 시범 시장에서는 브렌트 원유 선물과 S&P 500 지수가 산업 생산비에 대한 광범위한 에너지 시장의 영향을 반영하며 일관되게 최상위 중요도 요인으로 평가되어 왔다.[25]

## 수요 예측에서의 기후 및 기상 프록시 변수

기상 조건은 에너지 수요의 근본적 동인이며, 이는 다시 탄소배출권의 순환적 수요를 결정한다.[2, 3] 여름철 폭염이나 겨울철 강한 한파와 같은 극단적 기온 이상은 냉방 및 난방을 위한 전력 소비의 급격한 증가를 야기한다.[26, 27]

### 난방도일과 냉방도일 (HDD/CDD)

이러한 기후 기반 수요 변동을 포착하는 가장 효과적인 파생 변수는 난방도일 (Heating Degree Days, HDD) 과 냉방도일 (Cooling Degree Days, CDD) 이다.[26, 28] 이 변수들은 일평균 기온이 기준 쾌적 임계값 (통상적으로 난방의 경우 15.5℃, 냉방의 경우 22℃) 으로부터 벗어난 누적 편차를 측정한다.[28]

수식은 일반적으로 다음과 같이 표현된다.

$$\text{HDD} = \max(0, T_{\text{base}} - T_{\text{mean}})$$

$$\text{CDD} = \max(0, T_{\text{mean}} - T_{\text{base}})$$

HDD 와 CDD 의 연간 및 월간 합계는 에너지 수요의 기후 기반 구성 요소와 그에 관련된 CO₂ 배출에 대한 견고한 프록시 (proxy) 를 제공한다.[27, 28] 많은 지역에서 기온과 전력 수요 사이의 관계는 인간의 열적 쾌적과 관련된 최저점을 갖는 V 자 또는 U 자 곡선을 따른다.[26, 28] 이 임계치를 벗어나면 수요는 비대칭적으로 증가하며, 예를 들어 강한 한파는 겨울철 최대 전력 수요가 여름철 최대를 초과하게 만들고, 이는 석탄 화력 "피킹 (peaking)" 발전소의 가동을 크게 늘려 탄소 가격을 끌어올린다.[26]

또한 강수량과 (1965 년 이후 뚜렷한 계절 변동을 보여온) 지역적 온난화 추세 또한 수력발전의 가용성과 화력발전 냉각 시스템의 효율에 영향을 미치고, 이는 다시 전력망의 탄소 집약도에 영향을 미친다.[26, 27] 기후 불확실성 자체는 탄소 가격 변동성에서 중요한 요인이며, 시장 참여자들은 갑작스러운 수급 불균형을 촉발할 수 있는 극한 기상 사건의 위험을 헤지하기 때문이다.[25]

## 거시 경제 지표와 산업 생산량 효과

탄소배출권은 점차 광범위한 금융 시장과 동조화되어 주식이나 부동산과 같은 투자 자산처럼 행동해 왔다.[1, 29] 거시 경제 지표는 경제 성장이 에너지 소비 증가를 견인하고, 이로 인해 배출 및 배출권 수요가 증가하는 "생산 규모 효과 (output scale effect)"를 평가할 수 있게 해준다.[8, 30]

### GDP 성장과 디커플링 현상

전통적인 관점은 GDP 성장과 탄소 가격 사이의 직접적인 양 (+) 의 상관관계를 상정한다.[7, 8] 그러나 중국 시장의 실증 결과는 보다 복잡한 관계를 드러낸다. 일부 광역시에서는 경제 성장이 탄소 거래 가격과 양의 상관관계를 보이지만, 다른 성 (省) 에서는 음 (-) 의 상관관계를 나타낸다.[8] 이러한 차이는 산업 구조의 지역적 차이와 "녹색 (green)" 기술 혁신의 효과성에 기인한다.[8]

고도화된 모델은 STIRPAT(인구, 부유도, 기술에 대한 회귀에 의한 확률적 영향, Stochastic Impacts by Regression on Population, Affluence, and Technology) 프레임워크를 활용하여 이러한 동인들을 분해한다.[30] 이를 통해 연구자들은 "기술 진보 효과 (technology progress effect)"와 "에너지 집약도 효과 (energy intensity effect)"를 식별할 수 있는데, 이 둘은 탄소 배출에 대해 음 (-) 의 추진력으로 작용하여 경제 확장 시기에도 가격 상승을 잠재적으로 억제할 수 있다.[22, 30]

### 금융 시장 상호연결성

정교한 모델에서 예측변수로 사용되는 핵심 금융 변수에는 다음이 포함된다.

- **주가지수:** S&P 500, CSI 300, SSE 는 일반적인 경제 건전성과 투자자 정서의 프록시로 사용된다.[3, 25]
- **환율:** USD/CNY, EUR/CNY 와 같은 통화쌍은 에너지 수입의 상대적 비용과 탄소 집약 산업의 글로벌 경쟁력에 영향을 미친다.[11, 25]
- **금리:** 콜금리 및 채권 수익률은 배출 감축 투자의 자본 비용과 미래 배출권 희소성에 적용되는 할인율에 영향을 미친다.[8, 11]
- **변동성 지수:** VIX(CBOE 변동성 지수) 는 시장 전반의 위험 회피를 포착한다. 높은 VIX 수준은 흔히 유동성으로의 도피와 동시에 발생하며, 이는 탄소배출권의 매도세로 이어질 수 있다.[24, 31, 32]

최근 연구는 탄소 가격 충격이 거시 경제에 수축적·인플레이션적 효과를 미쳐 실질 GDP 의 감소와 금융 여건의 긴축으로 이어진다는 점을 기록해 왔다.[29, 33] 배출 집약도가 높은 기업 ("브라운 (brown) 기업") 에게 탄소 가격 상승은 투입 비용의 직접적인 증가를 의미하며, 이는 생산량 감소와 자산 가치의 하락으로 이어진다. 반면 "그린 (green) 기업"은 상대적인 이득을 볼 수 있다.[29, 33]

## 정책 충격, 규제 서프라이즈, 그리고 제도적 발동 요건

탄소배출권의 공급은 행정적 결정에 의해 정해지므로, 정책 발표와 규제 변화는 가격 시계열에서 구조적 단절 (structural break) 과 고빈도 노이즈의 주된 원천이다.[14, 34] 따라서 탄소 가격 예측을 위한 피처 엔지니어링은 이러한 제도적 개입을 정량화하는 변수를 반드시 포함해야 한다.[35]

### 탄소 정책 서프라이즈 도구 (Carbon Policy Surprise Instrument)

이 분야의 주요 혁신은 정책 뉴스의 외생적 (exogenous) 구성 요소를 분리해내는 "탄소 정책 서프라이즈" 도구의 개발이다.[10, 35] 이 도구는 배출권 캡 또는 시장안정화예비분 (MSR) 변경에 관한 발표와 같은 규제 사건 주변의 좁은 시간창 내에서 탄소 선물 가격의 백분율 변화를 측정하여 구성된다.[10, 36, 37]

해당 도구가 서로 다른 에너지 체제에서도 표준화되고 비교 가능하도록 보장하기 위해, 서프라이즈는 흔히 전일 도매 전력 가격으로 스케일링된다.[35] 수학적 표현은 다음과 같다.

$$\text{CPSurprise}_d = \frac{F_d^{\text{carbon}} - F_{d-1}^{\text{carbon}}}{p_{d-1}^{\text{elec}}}$$

여기서 $F_d^{\text{carbon}}$은 사건 발생일의 선물 가격이며, $p_{d-1}^{\text{elec}}$은 그 전일의 전력 가격이다.[35] 이러한 일별 서프라이즈는 월별 시계열로 집계되며, 규제 사건이 없는 달에는 0 의 값이 부여된다.[35] 이 파생 변수는 모델이 정책 주도 가격 충격을 COVID-19 팬데믹이나 2008 년 금융위기와 같이 동시에 발생하는 수요 측 교란으로부터 분리해낼 수 있도록 한다.[35, 38]

### 제도적 메커니즘: MSR 과 CBAM

EU ETS 의 시장안정화예비분 (MSR) 은 "유통 중인 배출권 총량 (Total Number of Allowances in Circulation, TNAC)"에 기반하여 경매 공급량을 조정하는 거래량 기반 규제장치 역할을 한다.[9, 39] TNAC 가 높으면 배출권을 예비분에 흡수하도록 발동되고, TNAC 가 낮으면 주입 (공급) 이 발동된다.[9, 40] 예측 모델은 이러한 발동 수준을 비선형 임계 변수로 다루어야 하며, 이는 시장이 이러한 한계점에 접근함에 따라 가격이 흔히 선반영적으로 (anticipatorily) 반응하기 때문이다.[15, 39]

탄소국경조정제도 (Carbon Border Adjustment Mechanism, CBAM) 는 EU ETS 가격을 수입 상품의 탄소 함량과 연동시킴으로써 가격 결정에 새로운 차원을 도입한다.[41, 42] 이는 사실상 "탄소 누출 (carbon leakage)"방지 부담금을 만들어내며, EU 탄소 인증서에 대한 수요를 외국 생산자에게까지 효과적으로 확장시킨다.[4, 41] EU 로의 수출에 대한 추가 부담을 나타내는 "CBAM 부담"과, 탄소 집약 상품에 대한 "무역 의존도"를 나타내는 파생 변수는 탄소 가격의 국제적 파급 효과를 분석하는 데 필수적이 되었다.[4, 43]

| 정책 수단 | 작용 메커니즘 | 예측을 위한 파생 변수 |
|---|---|---|
| 선형 감축 계수 (Linear Reduction Factor, LRF) | 총 캡의 연간 감소 | 시간 추세 변수 또는 계단 함수 (step-function) [15] |
| 시장안정화예비분 (Market Stability Reserve, MSR) | 잉여에 기반한 공급 조정 | 임계치까지의 거리 (distance-to-threshold); 흡수량 [9, 39] |
| CBAM | 탄소 가격에 기반한 수입 부담금 | 탄소 가격 차이; 부문별 수출 집약도 [4, 43] |
| 무상 할당 단계적 폐지 | 100% 경매로의 점진적 전환 | 이항 (binary) 전환 변수; 연도별 단계적 폐지율 [41, 44] |

## 비정형 데이터 및 정서 기반 피처 추출

탄소 시장은 "미시 시장 요인 (micro-market factors)"과 시장 참여자의 행동 편향에 크게 영향을 받으며, 이는 흔히 정형 경제 데이터에 반영되지 않는다.[1, 45] 인터넷 검색어, 뉴스 텍스트와 같은 비정형 데이터의 통합은 시장 정서와 기대를 정량화하는 경로를 제공한다.[1, 6, 46]

### 시장 주의 (Attention) 프록시로서의 검색어 지수

K-ETS 에서, 네이버 검색지수 (Naver Search Index) 는 강력한 단기 예측 변수로 입증되었다.[1] "탄소 피크", "탄소 거래", "배출권"과 같은 키워드는 환경 규제에 대한 대중과 기업의 인식 수준을 반영한다.[6, 25] 후행 거시경제 지표와 달리 검색 데이터는 "시장 참여자의 행위"에 대한 실시간 신호를 제공한다.[1] 다중회귀분석 (MRA) 을 사용한 연구자들은 이들 키워드의 수치적 영향력이 KAU 가격을 주간 단위로 효과적으로 예측할 수 있음을 입증했으며, 이는 4–8 주 앞서 운영을 계획하는 건설업과 같은 산업에 특히 가치가 있다.[1]

### 뉴스 정서 및 토픽 강도

자연어 처리 (NLP) 기법은 WiseSearch 와 같은 뉴스 데이터베이스에서 피처를 추출하기 위해 점차 폭넓게 사용되고 있다.[6] 합성곱 신경망 (CNN) 과 잠재 디리클레 할당 (Latent Dirichlet Allocation, LDA) 을 활용하여, 연구자들은 다음의 세 가지 주요 텍스트 지표를 구성한다.

- **시장 정서 지수 (Market Sentiment Index):** 정책 보고서와 공개 의견에서 강세 (bullish) 또는 약세 (bearish) 입장의 추출을 정밀화하기 위해 도메인 특화 탄소 시장 사전을 사용하여 도출한다.[6]
- **토픽 강도 지수 (Topic Intensity Index):** "재생에너지 보조금"이나 "탈석탄"등 특정 주제의 빈도와 부각 정도를 측정하며, 이는 다가오는 규제 변화의 신호가 된다.[6]
- **탄소 가격 트렌드 지수 (Carbon Price Trend Index):** 가격 변동에 대한 정성적 서사 (narrative) 를 포착하며, 이는 체제 전환의 초기 경고 신호를 제공할 수 있다.[6, 46]

실증 결과에 따르면, 이러한 다차원적 뉴스 피처의 도입은 "예측 정확도에서의 상당한 향상"을 가져오며, 특히 전통적 모델이 뒤처지는 경향이 있는 정책 불확실성이 높은 시기에 두드러진다.[6, 46]

## 재생에너지 통합과 간헐성 문제

풍력, 태양광 등 재생에너지원 (RES) 의 빠른 보급은 화석 연료에 대한 장기 수요를 감소시킴으로써 탄소 가격에 비선형적 하방 압력을 도입했다.[47, 48, 49] 그러나 이들의 간헐성은 "백업 (backup)"화석 연료 발전에 대한 단기 수요를 만들어내어 가격 신호를 복잡하게 만든다.[48, 50, 51]

### 간헐성 및 적정성을 위한 파생 피처

재생에너지가 탄소 가격에 미치는 영향을 포착하기 위해, 고도화된 모델은 다음과 같은 여러 파생 피처를 사용한다.

- **평균 가용성 vs. 가용성의 변동성 (Average Availability vs. Volatility of Availability):** 한 지역의 재생에너지원 부존량과 안정성을 나타낸다.[52] 풍력 가용성의 높은 변동성은 가스 화력 "피킹"발전소로의 전환을 빈번히 요구하며, 이는 탄소 가격 변동성의 급등을 야기한다.[48, 52]
- **발전–수요 공분산 (보너스–말러스, Bonus-Malus):** 재생에너지 발전과 도매 전력 가격 사이의 정렬을 측정하는 파생 변수이다.[53] 양 (+) 의 공분산 (보너스) 은 해당 기술이 수요와 잘 정렬되어 있음을 시사하며, 반면 음 (-) 의 공분산 (말러스) 은 "자기잠식 효과 (cannibalization effect)"를 나타내며, 이때 과잉 공급은 가격을, 그리고 그에 따라 탄소 수요를 0 에 가깝게 끌어내리게 된다.[53]
- **에너지 경제 비용 (Economic Cost of Energy, ECOE):** 균등화 발전 비용 (Levelized Cost of Energy, LCOE) 의 확장 개념으로, 생산량과 도매 가격 사이의 공분산을 측정하는 항을 추가하며, 장기적 "급전 순위 (merit order)"와 전력망의 탄소 집약도에 대한 더 우수한 예측 변수로 기능한다.[53]

미국과 EU 에서의 연구는 기후 정책 불확실성 (Climate Policy Uncertainty, CPU) 이 기업이 미래 규제에 대비해 헤지하면서 재생에너지 소비를 증가시키는 반면, 정책 캡이 정적으로 유지될 경우 재생에너지의 확장이 탄소 가격을 일시적으로 억제할 수 있음을 보여준다.[54, 55, 56]

## 고도화된 피처 엔지니어링과 분해 프레임워크

탄소 가격 시계열은 비정상성 (non-stationarity) 을 특징으로 하는데, 이는 통계적 특성이 시간에 따라 변한다는 것을 의미하며, 이 시계열은 고빈도 노이즈와 장기 구조적 패턴 모두를 포함한다.[6, 14] 고도화된 피처 엔지니어링은 신호를 분해하여 이러한 서로 다른 구성 요소들을 표적화된 방식으로 모델링할 수 있게 하는 것을 포함한다.[16, 25, 57]

### 신호 분해: EMD, VMD, ICEEMDAN

경험적 모드 분해 (Empirical Mode Decomposition, EMD) 와 변분 모드 분해 (Variational Mode Decomposition, VMD) 는 탄소 가격을 여러 개의 고유 모드 함수 (Intrinsic Mode Functions, IMFs) 로 분해하기 위해 자주 사용된다.[16, 25]

- **고주파 IMF:** 투기와 뉴스 충격에 의해 견인되는 단기 변동을 나타낸다.[16]
- **저주파 IMF:** 거시 경제 성장과 구조적 정책에 의해 견인되는 기저 추세를 나타낸다.[16, 25]
- **잔차 (residue) 구성 요소:** 장기 균형 경로를 포착한다.[16]

하이브리드 모델은 이러한 구성 요소들에 서로 다른 알고리즘을 적용하는 경우가 많으며, 예를 들어 비선형 고주파 IMF 에는 LSTM 을, 잔차에는 선형 회귀를 적용함으로써 RMSE 와 MAE 에서 유의한 개선을 달성한다.[14, 16, 25] 단절점 (breakpoint) 탐지 (예: PELT 또는 ICSS 알고리즘) 를 통한"구조 인식 (structural awareness)"의 통합은 모델이 갑작스러운 체제 전환에 적응하는 능력을 더욱 향상시킨다.[14, 58]

### 상호작용 변수와 데이터 전처리

효과적인 피처 엔지니어링은 또한 상호작용 항 (interaction terms) 의 생성과 다출처 데이터의 정규화를 포함한다.[57, 59]

- **상호작용 (Interactions):** "전반적 품질 (Overall Quality)"과"상태 (Condition)"(예: GDP × 배출 집약도) 를 결합하면, 성장과 규제 준수 사이의 숨겨진 관계를 발견할 수 있다.[59]
- **정규화 (Normalization):** S&P 500 지수와 지역별 탄소 가격과 같이 변수들의 스케일이 크게 다르므로, 큰 크기의 피처가 모델을 지배하지 않도록 Min-Max 정규화나 표준화가 필수적이다.[57, 60]
- **시차 피처 (Lagged Features):** K-ETS 에서 예측 오류는 4 번째 시차에서 일관되게 가장 낮으며, 이는 현재 가격이 4 주 전의 정보에 가장 강하게 영향을 받는다는 점을 시사한다.[1]

## 한국 배출권거래제 (K-ETS) 의 지역적 특수성

KAU 가격을 예측하려면, 높은 산업 집중도와 특정한 의무이행 주기를 특징으로 하는 한국의 독특한 제도적 환경에 대한 정밀한 이해가 요구된다.[11, 45]

### KAU, KCU, KOC 간 스프레드

K-ETS 모델에서 핵심적인 파생 변수는 한국 배출권 (Korean Allowance Units, KAU), 한국 상쇄배출권 (Korean Credit Units, KCU), 한국 외부사업감축실적 (Korean Offset Credits, KOC) 사이의 스프레드이다.[11, 45] 이 단위들은 기술적으로 1:1 로 교환 가능하지만, 거래량과 인증 범위의 차이로 인해 가격 차이가 불가피하다.[45] 예를 들어 KAU 는 정부가 할당하는 주요 배출권이며, KOC 는 외부 사업으로부터 도출된다.[45] KAU-KOC 스프레드는 "단기 차익거래 (arbitrage)"기회의 지표로 작용하며, 서로 다른 의무이행 시기 동안 특정 유형의 크레딧에 대한 시장의 선호를 반영한다.[45]

### 제도적 마감일과 가격의 계절성

K-ETS 는"의무이행 주기 (compliance cycle)", 특히 약속 기간 (commitment period) 다음 해의 2 월과 3 월에 배출량 명세서 보고서를 제출해야 하는 요건의 영향을 크게 받는다.[11] 통계적 분석에 따르면, 이러한 제도적 이항 (더미) 변수들은 KAU15 와 KAU16 가격 모두에 대해"공통적으로 유의 (commonly significant)"한 것으로 나타났는데, 이는 기업들이 검증된 의무를 충족하고 벌금을 회피하기 위해 배출권 확보에 분주해지기 때문이다.[11]

### 부상하는 시장안정화예비분 (MSR)

대한민국은 최근 K-ETS 를 위한 시장안정화예비분 (MSR) 메커니즘을 승인하였으며, 이는 4 기 (2026–2030) 에 영향을 미칠 예정이다.[13] 이 규칙 기반 메커니즘은 배출권 가격이나 거래량이 사전 설정된 임계치를 벗어나 움직일 때 경매 공급량을 조정하게 된다.[13] 예측 모델의 관점에서, "가격 밴드 임계치까지의 거리"와"계획된 배출권 예비량"은 향후 가장 핵심적인 파생 변수가 될 것이며, 이는 EU ETS 에서 관찰된 진화 양상을 반영한다.[12, 13] 시장 전문가들은 현재 KAU 가격이 2026 년에 29,000 원으로 상승하고, 캡이 강화되고 MSR 이 잉여 배출권의 회수를 시작함에 따라 2030 년에는 50,000 원에 도달할 잠재력이 있는 것으로 전망하고 있다.[61, 62]

## 종합 및 모델 개발에 대한 전략적 함의

여러 연구 흐름에 걸친 파생 변수에 대한 본 보고서의 포괄적 조사는 고성능 탄소 가격 예측 모델이 단순한 가격–지수 상관관계를 넘어, 다차원적이고 피처가 풍부한 프레임워크로 나아가야 한다는 점을 보여준다.

가장 효과적인 모델은 에너지 스프레드의"비용 압력 효과 (cost pressure effect)", 거시 경제 활동의"생산 규모 효과 (output scale effect)", 그리고 정책 발표의"서프라이즈 효과 (surprise effect)"를 통합하는 모델이다.[21, 29, 35] 특히 ICEEMDAN 과 같은 신호 분해 기법을, 검색어와 뉴스 정서로부터 추출한 비정형 데이터 피처와 결합하는 방식은 단기 투기적 노이즈와 장기 구조적 추세 모두에 대한 한층 정교한 이해를 가능하게 한다.[6, 16, 25]

K-ETS 모델을 개발하는 전문가들에게 있어서, 한국 시장 고유의 특성을 포착하기 위해서는 4 주 시차, KAU-KOC 스프레드, 제도적 마감일 더미를 우선순위화하는 것이 필수적이다.[1, 11, 45] 시장이 성숙하고 CBAM 과 같은 글로벌 메커니즘과 통합됨에 따라, 국제 에너지 변동성 (OVX) 과 지역 경제"디커플링"지표의 도입은 예측의 견고성을 더욱 향상시킬 것이다.[4, 16, 30] 궁극적으로, 이러한 고도화된 피처들은 이해관계자들이 탄소 가격에 내재된 비선형성을 항해 (navigate) 하고, 글로벌 기후 도전에 직면하여 보다 정보에 입각한 전략적 의사결정을 내릴 수 있도록 지원한다.[3, 6]

---

## 참고 문헌

1. Performance Comparison of Predictive Methodologies for Carbon ..., https://www.mdpi.com/2071-1050/14/13/8177
2. Effect Mechanism Research of Carbon Price Drivers in China—A Case Study of Shenzhen, https://pmc.ncbi.nlm.nih.gov/articles/PMC9517840/
3. Carbon Credits Price Prediction Model (CCPPM) - OPUS at UTS, https://opus.lib.uts.edu.au/rest/bitstreams/461f0803-c620-4550-94c4-d873601d74c9/retrieve
4. Macroeconomic Exposure to the EU's Carbon Border Adjustment Mechanism: The Case of the Middle East and Central Asia in - IMF eLibrary, https://www.elibrary.imf.org/view/journals/001/2025/182/article-A001-en.xml
5. Carbon Prices Forecasting Using Group Information - Energy RESEARCH LETTERS, https://erl.scholasticahq.com/article/36615-carbon-prices-forecasting-using-group-information
6. Carbon Trading Price Forecasting Based on Multidimensional News Text and Decomposition–Ensemble Model: The Case Study of China's Pilot Regions - MDPI, https://www.mdpi.com/2571-9394/7/4/72
7. 탄소배출권 가격의 결정 | click 경제교육, https://eiec.kdi.re.kr/material/clickView.do?click_yymm=201408&cidx=2211
8. (PDF) Economic Growth and Carbon Trading Prices: An Empirical Analysis Based on the Chinese Market - ResearchGate, https://www.researchgate.net/publication/403922769_Economic_Growth_and_Carbon_Trading_Prices_An_Empirical_Analysis_Based_on_the_Chinese_Market
9. EU reinforces the stability and predictability of its carbon market - European Commission, https://ec.europa.eu/commission/presscorner/detail/en/ip_26_666
10. Carbon Policy and Stock Returns: Signals from Financial Markets - International Monetary Fund, https://www.imf.org/-/media/files/publications/wp/2023/english/wpiea2023013-print-pdf.pdf
11. 한국 탄소배출권시장 가격결정체계의 학습효과 ... - 자원 · 환경경제연구, https://journal.resourceeconomics.or.kr/articles/pdf/oj4R/erer-2018-027-04-3.pdf
12. Approaches to Enhance the Market Functionality of the K-ETS - KDI - Korea Development Institute - RESEARCH, https://www.kdi.re.kr/eng/research/focusView?pub_no=18054
13. South Korea Approves Market Stability Reserve for K-ETS — OPIS - Morningstar, https://www.morningstar.com/news/dow-jones/20260427894/south-korea-approves-market-stability-reserve-for-k-ets-opis
14. A Hybrid Deep Learning based Carbon Price Forecasting Framework with Structural Breakpoints Detection and Signal Denoising - arXiv.org, https://arxiv.org/html/2511.04988v2
15. The long-term impact of the market stability reserve on the EU emission trading system, https://ideas.repec.org/a/eee/eneeco/v89y2020ics0140988320300852.html
16. A Carbon Price Prediction Model Based on the Secondary ... - MDPI, https://www.mdpi.com/1996-1073/14/5/1328
17. Blog - Spreads, Correlations and Cross-commodity Trades: Finding the Edge - Montel, https://montel.energy/resources/blog/spreads-correlations-and-cross-commodity-trades-finding-the-edge
18. Understanding Spark Spread: A Beginner's Guide to Power Plant Profitability, https://makayda.com/blog/understanding-spark-spread
19. Clean Dark Spread – Coal Margin After CO₂ Costs - Homaio, https://www.homaio.com/glossary/clean-dark-spread
20. Spark and dark spreads indicate improved profitability of natural gas, coal power plants - U.S. Energy Information Administration (EIA), https://www.eia.gov/todayinenergy/detail.php?id=66785
21. Spark Spread: A Key Metric for Profitability in Energy Trading - Morpher, https://www.morpher.com/blog/spark-spread
22. The Impact of Fossil Energy Prices on Carbon Emissions: The Dual Mediation of Energy Efficiency and Renewable Energy - MDPI, https://www.mdpi.com/1996-1073/18/23/6186
23. Application of Feature Engineering Techniques and Machine Learning Algorithms for Property Price Prediction - ResearchGate, https://www.researchgate.net/publication/389609191_Application_of_Feature_Engineering_Techniques_and_Machine_Learning_Algorithms_for_Property_Price_Prediction
24. CBOE Volatility Index Technical Analysis (VIX) - Investing.com, https://www.investing.com/indices/volatility-s-p-500-technical
25. Dynamic prediction of carbon prices based on the multi-frequency ..., https://pmc.ncbi.nlm.nih.gov/articles/PMC12190694/
26. Impact of Climate Change on Residential Electricity Consumption in Gwangju Metropolitan City by 2050 - 에너지경제연구, https://journal.keei.re.kr/articles/xml/MNMA/
27. The Impact of Temperature Trends on Short-Term Energy Demand - EIA, https://www.eia.gov/outlooks/steo/special/pdf/temptrnd.pdf
28. Large uncertainties in trends of energy demand for heating and cooling under climate change - PMC, https://pmc.ncbi.nlm.nih.gov/articles/PMC8408235/
29. The heterogeneous effects of carbon pricing: macro and micro evidence - Bank of England, https://www.bankofengland.co.uk/-/media/boe/files/working-paper/2024/the-heterogeneous-effects-of-carbon-pricing-macro-and-micro-evidence.pdf
30. Analysis of the carbon emission driving factors and prediction of a carbon peak scenario——A case study of Xi'an city - PMC, https://pmc.ncbi.nlm.nih.gov/articles/PMC9703453/
31. Top 8 Volatility Indicators That Every Trader Should Know - IG, https://www.ig.com/en-ch/trading-strategies/are-these-the-8-best-volatility-indicators-traders-should-know--230427
32. Profit By Combining RSI And VIX - Helping you Master EasyLanguage, https://easylanguagemastery.com/strategies/vix-rsi/
33. QUANTITATIVE ANALYSIS OF THE IMPACTS OF CARBON PRICING ON ENERGY INFLATION IN THE EUROPEAN UNION - Knowledge UChicago, https://knowledge.uchicago.edu/record/6099/files/MA_Thesis_MSafonov.pdf
34. (PDF) Do carbon policy shocks move stocks? evidence from China's carbon market, https://www.researchgate.net/publication/403639739_Do_carbon_policy_shocks_move_stocks_evidence_from_China's_carbon_market
35. Unraveling the impact of a carbon price shock on ... - BBVA Research, https://www.bbvaresearch.com/wp-content/uploads/2025/04/WP-25-04.pdf
36. Carbon Policy Surprises and Stock Returns: Signals from Financial Markets, WP/23/13, January 2023, https://repository.graduateinstitute.ch/record/301037/files/null-001.2023.issue-013-en.pdf
37. The economic consequences of putting a price on carbon - European Central Bank, https://www.ecb.europa.eu/press/conferences/ecbforum/shared/pdf/2021/kaenzig_paper.en.pdf
38. NBER WORKING PAPER SERIES CLIMATE POLICY AND THE ECONOMY: EVIDENCE FROM EUROPE'S CARBON PRICING INITIATIVES Diego R. Känzig Max, https://www.nber.org/system/files/working_papers/w31260/w31260.pdf
39. Preparing the review of the Market Stability Reserve – ERCST, https://ercst.org/preparing-the-review-of-the-market-stability-reserve/
40. Is a Market Stability Reserve likely to improve the functioning of the EU ETS?, https://climatestrategies.org/publication/is-a-market-stability-reserve/
41. Carbon Border Adjustment Mechanism - Taxation and Customs Union, https://taxation-customs.ec.europa.eu/carbon-border-adjustment-mechanism_en
42. Working Paper Series - The EU's CBAM: implications for member states and trading partners - European Central Bank, https://www.ecb.europa.eu/pub/pdf/scpwps/ecb.wp3177~c5feb7f15a.en.pdf
43. Quantitative Assessment of the Carbon Border Adjustment Mechanism: Impacts on China–EU Trade and Provincial-Level Vulnerabilities - MDPI, https://www.mdpi.com/2071-1050/17/4/1699
44. The impact of carbon pricing and a CBAM on EU competitiveness - De Nederlandsche Bank, https://www.dnb.nl/media/xdlitfni/dnb-analyse-the-impact-of-carbon-pricing-and-a-cbam-on-eu-competitiveness.pdf
45. Granger causality of Carbon allowances and Carbon offsets in the Korean carbon market. - Scholars Journal Publishing House, https://scholarsjournal.net/ijier/article/download/3785/2585/12842
46. The role of online news sentiment in carbon price prediction of China's carbon markets - PMC, https://pmc.ncbi.nlm.nih.gov/articles/PMC9838308/
47. JSDEWES: Analysing the Influence of Carbon Prices on Users' Energy Cost and the Positive Impact of Renewable Energy Sources - SDEWES Centre, https://www.sdewes.org/jsdewes/pid13.0582
48. Renewable Energy and Carbon Intensity: Global Evidence from 184 Countries (2000–2020), https://www.mdpi.com/1996-1073/18/13/3236
49. RETRACTED: Exploring the impact of renewable energy on economic growth and carbon emissions: Evidence from partial least squares structural equation modeling - PMC, https://pmc.ncbi.nlm.nih.gov/articles/PMC10712851/
50. Intermittency and the Value of Renewable Energy | Journal of Political Economy: Vol 124, No 4, https://www.journals.uchicago.edu/doi/10.1086/686733
51. Energy Transition with Variable and Intermittent Renewable Electricity Generation - ifo Institut, https://www.ifo.de/DocDL/cesifo1_wp7442.pdf
52. Impact of renewable energy intermittency and carbon tax on investment strategy for grid-connected microgrid in China - AIP Publishing, https://pubs.aip.org/aip/jrse/article-pdf/doi/10.1063/5.0222909/20414074/015909_1_5.0222909.pdf
53. "Pricing intermittent renewable energy" - Toulouse School of Economics, https://www.tse-fr.eu/sites/default/files/TSE/documents/doc/wp/2025/wp_tse_1653.pdf
54. Untangling Carbon–Clean Energy Dynamics: A Quantile Granger-Causality Perspective, https://www.mdpi.com/2071-1050/17/7/3118
55. Interplay Between Renewable Energy Consumption and Prices, Climate Policy Uncertainty, and CO2 Emissions: Insights for Environmental Sustainability, https://erl.scholasticahq.com/article/146299-interplay-between-renewable-energy-consumption-and-prices-climate-policy-uncertainty-and-co2-emissions-insights-for-environmental-sustainability
56. Interplay Between Renewable Energy Consumption and Prices, Climate Policy Uncertainty, and CO2 Emissions: Insights for Environmental Sustainability, https://erl.scholasticahq.com/article/146299
57. Perception and Prediction of Factors Influencing Carbon Price: Multisource, Spatiotemporal, Hierarchical Federated Learning Framework with Cross-Modal Feature Fusion - PMC, https://pmc.ncbi.nlm.nih.gov/articles/PMC12693995/
58. Carbon market volatility analysis based on structural breaks: Evidence from EU-ETS and China - Frontiers, https://www.frontiersin.org/journals/environmental-science/articles/10.3389/fenvs.2022.973855/full
59. Feature Engineering for House Prices - Kaggle, https://www.kaggle.com/code/ryanholbrook/feature-engineering-for-house-prices
60. Advanced Feature Engineering and Machine Learning Techniques for High Accurate Price Prediction of Heterogeneous Pre-Own Cars - MDPI, https://www.mdpi.com/2624-8921/7/3/94
61. "탄소배출권 KAU, 내년 2.9 만원 전망…2030 년 5 만원대" - 머니투데이, https://www.mt.co.kr/stock/2025/10/14/2025101317311927080
62. 국내 탄소배출권 가격, "내년 2 만원, 5 년 뒤 5 만원 돌파 전망", https://www.esgeconomy.com/news/articleView.html?idxno=13059
