# Requirement Analysis Notes — Music Streaming Analytics

## 1. Business Context

This project analyzes a mid-size music streaming platform using four years of operational data from 2021 to 2024. The data covers listening behaviour, subscription lifecycle, content catalogue, user demographics, revenue/MRR, churn, retention, and fraud/anomaly indicators across 10 markets.

The business wants to understand where growth opportunities exist, where revenue or churn risks appear, which user and content segments perform strongly, and what actions stakeholders should take next.

## 2. Primary Business Problem

The platform needs to improve business performance by identifying revenue growth opportunities, reducing churn risk, understanding engagement drivers, optimizing content and market investment, and detecting suspicious or anomalous activity.

## 3. Target Stakeholders

### Executive / Leadership Team
Needs:
- Overall business health
- MRR, ARPU, churn, retention, engagement trends
- Key opportunities and risks
- Top recommendations

### Revenue / Subscription Team
Needs:
- MRR expansion and contraction
- Revenue by tier, country, and cohort
- Churn revenue and downgrade impact
- Free-to-paid conversion opportunities

### Retention / CRM Team
Needs:
- Pre-churn behaviour
- Engagement differences by user segment
- High-risk customer groups
- Retention campaign opportunities

### Content / Product Team
Needs:
- Top artists, tracks, genres, and playlists
- Content performance by country, age, device, and tier
- Recommended vs non-recommended content performance
- Playlist and genre affinity

### Risk / Operations Team
Needs:
- Fraud cluster behaviour
- Suspicious listening patterns
- Revenue or usage anomalies
- Data quality issues

## 4. Core Business Questions

1. How healthy is the platform’s overall business performance across MRR, ARPU, churn, and engagement from 2021 to 2024?

2. Which subscription tiers, countries, and cohorts drive the most revenue growth, and where is MRR being lost through churn or downgrades?

3. What listening behaviours are associated with retention, churn, and conversion from free to paid?

4. Which artists, tracks, genres, playlists, countries, and user segments over-index in engagement or revenue compared with the platform baseline?

5. How does the fraud-flagged segment behave differently from regular users, and what unusual patterns should the business investigate further?

## 5. Expected KPIs

### Revenue & Subscription
- Total MRR
- Net MRR Change
- Expansion MRR
- Contraction MRR
- Churn Revenue
- ARPU
- Paid Users
- Free Users
- Churn Rate
- Upgrade Count
- Downgrade Count
- Signup Count
- Retention Event Count

### Customer Behaviour
- Listening Sessions
- Listening Duration
- Average Session Duration
- Skip Rate
- New Artist Discovery
- Active Users
- Sessions per User
- Engagement by Tier
- Engagement by Age Cohort
- Engagement by Country

### Content & Catalogue
- Plays by Artist
- Plays by Track
- Plays by Genre
- Revenue by Content
- Recommended vs Non-Recommended Performance
- Playlist Engagement
- Genre Over-Index by Country

### Fraud / Risk
- Fraud Cluster User Count
- Fraud Cluster Listening Volume
- Fraud Cluster Revenue
- Suspicious High-Volume Users
- Anomalous Session Patterns

## 6. Scope

### Must-have
- Executive summary with headline KPIs
- Revenue and MRR trend
- Subscription lifecycle analysis
- Churn and revenue-at-risk view
- Engagement analysis by tier, country, age, and device
- Content performance analysis
- Fraud cluster comparison
- At least one over-index or cohort comparison
- Actionable recommendations

### Nice-to-have
- Pre-churn behaviour analysis
- Heavy free user conversion analysis
- Country × genre over-index
- Device × genre affinity
- Playlist composition analysis
- Cohort revenue comparison
- Leading indicator framework

### Out of Scope
- Advanced machine learning churn prediction
- Recommendation engine
- Complex fraud detection model
- Real-time dashboard
- More than 4 dashboard pages
- Deep statistical modelling
- Analysis of every possible field combination

## 7. Key Data Questions to Confirm from DATA_DICTIONARY.md

1. What is the grain of the listening sessions fact table?
2. What is the grain of the subscription events fact table?
3. How is MRR before, MRR after, and MRR change defined?
4. How is churn defined?
5. How is retention defined?
6. How is ARPU expected to be calculated?
7. Is session-level revenue separate from subscription MRR?
8. How are Free, paid, family, and fraud users identified?
9. How should the playlist-track bridge be used without double counting?
10. Which date should be used for each analysis: session date, event date, signup date, or churn date?

## 8. Main Risks

- Mixing session-level revenue with MRR incorrectly.
- Double counting users when joining user dimensions to listening sessions.
- Double counting revenue when joining subscription events to sessions.
- Double counting tracks when using the playlist-track bridge.
- Treating all top-N rankings as insights without comparing against baselines.
- Making causal claims from descriptive data.
- Calling a pattern a churn predictor without validation.
- Creating too many pages and losing the business story.

## 9. Dashboard Plan

### Page 1: Executive Summary
Purpose:
Show overall business health, key trends, major risks, and top recommendations.

### Page 2: Revenue & Subscription Health
Purpose:
Explain MRR, ARPU, churn revenue, subscription events, expansion, contraction, and conversion.

### Page 3: Customer Engagement & Churn Risk
Purpose:
Connect listening behaviour with retention, churn, tier, age, country, and conversion potential.

### Page 4: Content, Market & Fraud Insights
Purpose:
Identify content winners, market opportunities, over-indexing patterns, and suspicious behaviour.
