

**Portfolio for Great Lockdown**

6학사

2017103757 소프트웨어융합학과 정희재

2015103604 수학과 한지운

2014102714 국제학과 엄세웅





**Contents**

**Portfolio for Great Lockdown**

**01 02 03 04**

**주제**

**이론 분석**

**구현**

**시연**

주제 선정

All Weather

Risk Parity

All Weather

60/40

Sample & Code

GMV

Backtest





**01 주제**

001 주제선정





Part 1

**주제 선정**

**한미일 주가 지수**

**-21%**

**2020년 주식시장의 최고 이슈 : 코로나**

1929년 대공황 (Great Depression)

↓

2008년 대침체 (Great Recession)

↓

2020년 대봉쇄 (Great Lockdown)

**S&P**

**Nikkei**

**KOSPI**





Part 1

**주제 선정**

**세계적인 대공황을 가장 잘 방어할 수 있는 포트폴리오는 없을까?**





**02 이론 분석**

001 All Weather Portfolio

002 Risk Parity

003 Sample & Code





Part 2

**All Weather Portfolio**

Conventional Portfolio Risk Impact

All Weather Portfolio Risk Impact

**12%**

**88%**

**Equity**

**Others**

**Bond**

**Inflation**

**Equity**

**etc**

출처 : Bridgewater The All Weather Strategy





Part 2

**All Weather Portfolio**

**거시경제적 특정 경제상황에 대한 리스크 헤지**

**Growth**

**25% Risk**

**Inflation**

경제적 상황에 따라 변화하는 Correlation

Inflation에 대한 기대감 >> Correlation ↑

경제성장에 대한 기대감 >> Correlation ↓

주식

**25% Risk**

물가연동채권

회사채

원자재

**Rising**

**Falling**

원자재

이머징국가 채권

이머징국가 채권

**25% Risk**

**25% Risk**

Correlation 기반한 투자 >> 경제상황에 기반한 투자

4가지 경제상황에 따른 상승 / 하락하는 자산 투자로 인한 Risk Hedge

자산군 내에서도 Risk Hedge를 위해 ETF 활용

국채

주식

국채

물가연동채권

출처 : Bridgewater The All Weather Strategy





Part 2

**Risk Parity**

**Mean Variance Model**

M-V Model 계산을 위해 공분산, **기대수익률**, 위험회피계수 등 필요

**기대 수익률** : 추정에러가 높고 신뢰도가 낮음

**Risk Parity Model**

전체 포트폴리오에 미치는 **위험기여도**가 동일하도록 구성

**공분산 행렬**을 가지고 계산

출처 : 한국투자증권 – Risk Parity Strategy





Part 2

**Risk Parity**

**Marginal Risk Contribution**

**Risk Parity Model**

**Risk Contribution**

전체 포트폴리오에 미치는 **위험기여도**가 동일하도록 구성

**공분산 행렬**을 가지고 계산

출처 : 한국투자증권 – Risk Parity Strategy





Part 2

**Risk Parity**

**– Risk Contribution**

**Risk Contribution**

**Risk Parity Model**





Part 2

**Risk Parity**

**– Code**

**Risk Parity Model**

출처 : Henry’s Quantopia – Risk Parity(Python)





Part 2

**Risk Parity**

**– Sample**

**Weight**

**0.7**

**0.6**

**0.5**

**0.4**

**0.3**

**0.2**

**0.1**

**0**

**Sample Portfolio**

Asset 1 : Equity

**Equity**

**IL Bond**

**Comm**

Asset 2 : Inflation- Linked Bond

Asset 3 : Commodities

**RC**

**0.35**

**0.3**

**0.25**

**0.2**

**0.15**

**0.1**

**0.05**

**0**

**Equity**

**IL Bond**

**Comm**





Part 2

**All Weather Portfolio by Risk Parity**

**Growth**

**Inflation**

주식

물가연동채권

원자재

회사채

원자재

**Rising**

**Falling**

**All Weather Portfolio**

이머징국가 채권

이머징국가 채권

각 거시경제적 상황별에 포함된 자산으로 동일 가중 Portfolio를 만든 후

4개의 Asset으로 Risk Parity model 실행

국채

주식

국채

물가연동채권





**03 구현**

001 활용자산

002 비교군





Part 3

**투자 자산**

Global Nominal Bond

**채권**

1Y+

iShares 1-3 Year Treasury Bond ETF

10Y+

20Y+

30Y+

iShares 10-20 Year Treasury Bond ETF

iShares 20+ Year Treasury Bond ETF

Vanguard Extended Duration Treasury Index Fund ETF Shares

Global Nominal Bonds : 국채 및 국채 연동 채권

Global Inflation-linked Bonds : 물가연동채권

EMD Spread : 이머징 마켓 채권

Global Inflation-linked bonds

US

US

iShares TIPS Bond ETF

US Corporate Debt Spreads

Corporate Debt Spreads : 회사채

iShares iBoxx $ Investment Grade Corporate Bond ETF

Global Equities

Vanguard Total Stock Market Index Fund ETF Shares

iShares S&P 500 Index Fund Class K

iShares MSCI Japan ETF

All

US

**주식**

Japan

Europe

SPDR EURO STOXX 50 ETF

각국의 지수를 기반으로 한 주식 ETF 활용

EMD Spreads

iShares J.P. Morgan USD Emerging Markets Bond ETF

iShares Latin America 40 ETF (ILF)

iShares MSCI Brazil ETF

All

Latin America

Brazil

**원자재**

Commodities

iShares Gold Trust

Gold

All

Invesco DB Commodity Index Tracking Fund

Invesco DB Agriculture Fund

United States Oil Fund, LP

금, 농산물, 원유, 금속 기반으로한 ETF 활용

농산물

Oil

금속

Invesco DB Base Metals Fund





Part 3

**웹구현**





Part 3

**비교군**

**60/40 Portfolio**

전통적 포트폴리오

주식 60 : 채권 40

Rebalance 기간마다 weight를 60 : 40으로 수정

**GMV Portfolio**

**All Weather Portfolio**

분산 최소화 포트폴리오

4가지 거시경제적 상황에 위험기여도를 동일한 비중으로 투자

선형계획법 모형 적용

Risk Parity 적용

Rebalance 기간마다 GMV에 따라 자산 할당을 조정하는 동적자산배분

Rebalance 기간마다 Risk Parity를 활용하여 자산 할당 조정





Part 3

**Backtest**

Rebalance 전까지 Balance 계산

↓

Rebalance Date

60/40 Model : Weight 60 : 40으로 조정

MV & AWF : Lookback을 기준으로 Weight 계산후 조정

↓

Repeat





Part 3

**Case Study**

**Input :**

Bond : 1year+ bond ETF

Inflation-linked : TIPS Bond ETF

Corp Spreads : Corporate Bond ETF

Equity : Total Stock Market Index Fund

EMD : MSCI Brazil ETF

Comm : Commodity Index Tracking Fund





Part 3

**Case Study**

**Drawdown**

**Cumulative Rate of Return**

**Monthly/ Annual**





Part 3

**Case Study**

**Drawdown**

**Cumulative Rate of Return**

**Monthly/ Annual**





Part 3

**Case Study**

**OLS with 5-Factor Model**

**60/40**

**AWP**

**M-V**





Part 3

**Case Study**

**Summary**

**60/40**

2473.46

7.36%

-33.73%

0.19

**GMV**

1579.73

3.65%

-29.06%

0.13

**AWP**

1837.10

4.88%

-21.64%

0.16

Final Balance

CAGR

MDD

Sharpe Ratio

VaR

-1.12

-0.49

-0.68

CVaR

-1.90

-0.98

-1.10





FDA Final Project

Portfolio for Great Lockdown

6 학 사

**Q A**

**&**

