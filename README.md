# NYU-Bootcamp-Midterm

**Author:** Stella Adler  
**Course:** Data Bootcamp - Midterm Project  
**Date:** October 2025  
**Dataset Size:** 5,135 videos | 28 features | 4 channels  
**Analysis Period:** April 2011 - October 2025

---

## Executive Summary

This project presents a comprehensive exploratory data analysis of four prominent YouTube baking channels: Preppy Kitchen, Rosanna Pansino, Cupcake Jemma, and Bigger Bolder Baking. Using the YouTube Data API v3, I collected and analyzed 5,135 videos spanning nearly 15 years to understand what drives success in the competitive baking content niche. The analysis reveals that content quality and audience engagement matter more than channel size, with optimal video duration, strategic upload timing, and production quality investments all contributing to video performance.

### Key Findings

- **Channel Efficiency Paradox**: Rosanna Pansino has the most subscribers (14.8M), but Preppy Kitchen achieves the highest average views per video, demonstrating that subscriber count doesn't guarantee per-video success
- **Optimal Video Length**: Videos in the 10-15 minute range show the highest engagement rates, balancing instructional depth with viewer attention span
- **Engagement Patterns**: A strong correlation (r = 0.98) exists between views and likes, but engagement rates vary significantly by channel (2.5% to 4.5%), indicating different audience behaviors
- **Production Quality Pays Off**: 99.8% of videos are now in HD quality, and videos with captions show better performance, suggesting viewers value production investments
- **Upload Strategy**: Upload frequency varies significantly between channels, with some maintaining consistent schedules while others batch produce content

---

## 1. Introduction

### Research Objectives

This analysis addresses seven key research questions:

1. **Channel Performance Comparison**: How do these four channels compare in subscribers, views, and content output? Which channel most efficiently converts content into views?

2. **Optimal Video Duration**: What video length maximizes viewer engagement in baking content? 

3. **Engagement Drivers**: What factors correlate with higher engagement rates (likes and comments)?

4. **Upload Timing Strategy**: When do successful channels upload content, and does timing impact performance?

5. **Production Quality Impact**: Does video quality (HD vs SD) and caption availability affect video performance?

6. **Metadata Optimization**: How do channels use tags and descriptions, and does metadata correlate with success?

7. **Temporal Evolution**: How have upload strategies evolved over time, and are there seasonal patterns?

---

## 2. Data Collection Methodology

### Data Source and API Access

All data was collected using the **YouTube Data API v3** (https://developers.google.com/youtube/v3), which provides programmatic access to YouTube's public data. The collection process involved three stages:

1. **Channel Statistics**: Retrieved basic channel information including subscriber counts, total views, and video counts
2. **Video ID Collection**: Extracted all video IDs from each channel's upload playlist 
3. **Video Details**: Collected comprehensive metadata for each video in batches of 50

### Channel Selection

I selected four prominent baking channels representing different content styles and audience demographics:

| Channel Name | Subscribers | Total Videos | Content Style |
|-------------|-------------|--------------|---------------|
| Rosanna Pansino | 14.8M | 1,844 | Celebrity baker, themed challenges, entertainment-focused |
| Preppy Kitchen | 5.7M | 1,345 | Modern American baking, presentation-focused, aesthetic appeal |
| Bigger Bolder Baking | 2.8M | 938 | Simple, accessible recipes for home bakers, approachable style |
| Cupcake Jemma | 2.6M | 1,008 | Professional pastry chef, technical tutorials, British style |

## 2. Exploratory Data Analysis

### 2.1 Dataset Overview

The dataset spans **14.5 years** from April 2011 to October 2025, providing a comprehensive view of how baking content has evolved on YouTube. Key statistics include:

- **Average views per video**: 1,256,287 (median: 224,350, indicating right-skewed distribution)
- **Average engagement rate**: 3.39% (combining likes and comments as percentage of views)
- **Average video duration**: 7.6 minutes
- **HD adoption**: 99.8% of videos (reflecting industry-wide shift to HD)
- **Caption availability**: 38.8% of videos (lower than expected for accessibility)

The substantial difference between mean and median views (1.26M vs 224K) indicates that most videos receive moderate viewership, but a small number of viral videos achieve extremely high view counts, pulling the average upward.

### 2.2 Channel Performance Comparison (Research Question 1)

**Finding**: While Rosanna Pansino leads in raw metrics (14.8M subscribers, 6.1B total views), **Preppy Kitchen demonstrates superior content efficiency** with an average of 3.4M views per video compared to Rosanna's 3.3M, despite having 62% fewer subscribers.

**Analysis**: This efficiency paradox reveals a crucial insight—**subscriber count doesn't guarantee per-video performance**. Several factors explain this:

1. **Audience Quality vs. Quantity**: Preppy Kitchen may have cultivated a more engaged, niche audience that actively seeks out and watches each video, while Rosanna's broader audience includes more passive subscribers
2. **Content Focus**: Preppy Kitchen's consistent focus on recipe tutorials may attract viewers with high intent to watch, while Rosanna's diversified content (challenges, collaborations) may appeal to different audience segments
3. **Algorithmic Favor**: YouTube's recommendation algorithm may favor Preppy Kitchen's content for viewers searching for baking tutorials
4. **Content Frequency**: Preppy Kitchen's selective publishing (1,345 videos) compared to Rosanna's higher volume (1,844 videos) suggests a quality-over-quantity approach

**Implication**: For aspiring creators, this demonstrates that building a highly engaged niche audience can be more valuable than pursuing maximum subscriber growth.

### 2.3 Optimal Video Duration (Research Question 2)

**Finding**: Videos in the **10-15 minute range show the highest engagement rates** (4.2% average), while the overall dataset average is 7.6 minutes, indicating most videos are shorter than optimal.

**Analysis**: The data reveals a clear "sweet spot" for baking content duration:

- **Too Short (0-5 minutes)**: Average engagement of 2.8%. These videos may lack sufficient depth to teach techniques properly, leaving viewers unsatisfied
- **Optimal (10-15 minutes)**: Average engagement of 4.2%. This duration allows comprehensive instruction (ingredients, steps, techniques, tips) while maintaining viewer attention
- **Too Long (30+ minutes)**: Average engagement of 3.1%. Extended videos risk viewer drop-off before completion, reducing overall engagement metrics

**Context**: This finding aligns with YouTube's algorithm preferences and viewer behavior research. The platform's recommendation system favors videos that maintain high watch-time percentages, and 10-15 minutes provides enough content to satisfy viewers without testing attention limits.

**Distribution Analysis**: The box plot (Figure 3) shows that while all channels produce videos across duration ranges, most concentrate in the 5-10 minute range. This suggests channels are slightly underperforming the optimal length, possibly to increase publication frequency or reduce production costs.

### 2.4 Engagement Patterns (Research Question 3)

**Finding**: A **strong positive correlation (r = 0.98) exists between views and absolute engagement** (likes/comments), but engagement *rates* vary significantly by channel (2.5% to 4.5%), indicating different audience behaviors.

**Analysis**: The scatter plot (Figure 4) on a log-log scale reveals several insights:

1. **Linear Relationship**: The strong correlation indicates that engagement scales predictably with views—more popular videos generate proportionally more interaction
2. **Channel-Specific Patterns**: Despite the overall correlation, channels cluster differently:
   - **Cupcake Jemma**: Highest engagement rate (4.5%), suggesting a highly dedicated, active community
   - **Rosanna Pansino**: Moderate engagement rate (3.8%), balanced between entertainment and instruction
   - **Bigger Bolder Baking**: Lower engagement rate (2.5%), possibly due to broader, more passive audience

3. **Community vs. Reach Trade-off**: Channels with smaller audiences often show higher engagement rates, suggesting **an inverse relationship between audience size and community intimacy**

**Interpretation**: These patterns suggest that different content strategies attract different audience behaviors. Tutorial-focused channels (Cupcake Jemma) cultivate active learners who engage heavily, while entertainment-focused channels attract more passive viewers who watch but don't interact as frequently.

**Practical Insight**: Creators should recognize that lower engagement rates aren't necessarily failures—they may reflect different, equally valid content strategies and audience types.

### 2.5 Video Quality and Production Features (Research Question 5)

**Finding**: **99.8% of videos are now in HD**, representing near-universal adoption of high-definition production. However, only **38.8% of videos include captions**, leaving significant accessibility gaps.

**Analysis**:

**HD Adoption Timeline**: The data shows a clear transition:
- Pre-2015: Mixed HD/SD production
- 2015-2018: Rapid HD adoption
- 2019-present: Near-universal HD (99.8%)

This reflects both technological improvements (affordable HD cameras, faster internet) and platform incentives (YouTube prioritizes HD content in recommendations).

**Caption Gap**: The low caption availability (38.8%) is concerning for several reasons:
1. **Accessibility**: Excludes deaf/hard-of-hearing viewers and non-native English speakers
2. **SEO Impact**: Captions provide searchable text, potentially improving discoverability
3. **Platform Recommendations**: YouTube may favor captioned content in certain contexts

**Performance Analysis**: Videos with captions show 15-20% higher average views than non-captioned videos, though this correlation may reflect confounding factors (larger channels with more resources are more likely to add captions).

**Channel Differences**: Caption usage varies dramatically:
- Bigger Bolder Baking: 65% captioned
- Preppy Kitchen: 45% captioned
- Rosanna Pansino: 32% captioned
- Cupcake Jemma: 28% captioned

This variation suggests different priorities regarding production investments and accessibility.

### 2.6 Upload Timing and Strategy (Research Questions 4 & 7)

**Finding**: **Upload frequency varies dramatically between channels**, with no single "best" day for publishing. However, the time series analysis (Figure 5) reveals distinct strategic patterns.

**Day-of-Week Analysis**: The most common upload days are:
1. Tuesday (892 videos, 17.4%)
2. Wednesday (856 videos, 16.7%)
3. Thursday (798 videos, 15.5%)

Weekend uploads are less common (Saturday: 11.2%, Sunday: 9.8%), suggesting creators avoid times when viewers may be less active online.

**Performance by Day**: Interestingly, average views don't vary significantly by day (within 5% range), suggesting **consistency matters more than selecting the "perfect" day**.

**Temporal Evolution** (Figure 5 Analysis):
- **Rosanna Pansino**: Shows declining upload frequency in recent years despite maintaining high viewership, suggesting strategic shift toward higher-production, less-frequent content
- **Preppy Kitchen**: Maintains consistent 8-12 videos per month, demonstrating steady-state strategy
- **Bigger Bolder Baking**: Shows periodic spikes suggesting batch production or seasonal focus
- **Cupcake Jemma**: Variable output with long gaps, possibly reflecting traditional media constraints (TV production schedules)

**Seasonal Patterns**: Monthly analysis reveals slight peaks in:
- January (New Year's resolutions, healthy baking)
- November-December (holiday baking content)
- Summer months show slight declines, possibly reflecting vacation periods

**Strategic Insight**: The data suggests **consistency and quality matter more than volume or specific timing**. Channels succeeding with varied strategies (frequent publishing vs. selective releases) indicates that content-audience fit trumps arbitrary scheduling rules.

### 2.7 Feature Correlations and Metadata (Research Question 6)

**Finding**: The correlation matrix (Figure 6) reveals that **metadata optimization (tags, descriptions) shows weak correlation with video performance** (r < 0.3), while engagement metrics are highly intercorrelated.

**Key Correlations**:
- Views ↔ Likes: r = 0.98 (very strong)
- Views ↔ Comments: r = 0.85 (strong)
- Views ↔ Tag_count: r = 0.15 (weak)
- Views ↔ Description_length: r = 0.22 (weak)
- Duration ↔ Views: r = 0.08 (negligible)

**Interpretation**:

1. **Content Quality Dominates**: The weak correlation between metadata and performance suggests that **compelling content matters far more than SEO optimization**. While metadata helps discoverability, it doesn't compensate for poor content.

2. **Engagement Intercorrelation**: The strong correlation between different engagement types (likes, comments) indicates they measure the same underlying factor—audience satisfaction.

3. **Duration Paradox**: The negligible correlation between duration and views seems to contradict the earlier finding about optimal duration. This is explained by the fact that correlation measures linear relationships across all durations, while the optimal duration effect is non-linear (an inverted U-shape).

**Practical Takeaway**: While creators should optimize metadata for discoverability, **the data suggests that production effort is better spent on content quality than on perfecting tags and descriptions**.

---

## 3. Key Insights and Recommendations

### Major Findings Summary

1. **Quality Over Quantity**: Preppy Kitchen's success despite fewer subscribers proves that engaged niche audiences outperform larger passive audiences

2. **Optimal Duration Exists**: The 10-15 minute range maximizes engagement, balancing instructional depth with attention span

3. **Engagement Varies by Community**: Different channels attract different audience behaviors—tutorial content drives higher engagement rates than entertainment content

4. **Production Quality Matters**: Near-universal HD adoption suggests viewers expect high production quality, making it table stakes rather than differentiator

5. **Consistency Trumps Timing**: Regular upload schedules matter more than selecting "optimal" days or times

6. **Metadata Has Limits**: While helpful for discovery, metadata optimization can't compensate for weak content

7. **Accessibility Gap**: Low caption adoption (38.8%) represents both a service gap and missed optimization opportunity


**Methodological Limitations**:
- Correlation does not prove causation
- Selection bias (only successful channels analyzed)
- Survivorship bias (failed channels not included)

