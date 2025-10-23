# NYU-Bootcamp-Midterm


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

1. Which channel demonstrates the strongest overall performance, and how does audience scale affect content efficiency?

2. What is the optimal video duration for maximizing engagement?

3. Does audience size significantly influence engagement efficiency across top baking channels?

4. What relationships exist between video features and engagement performance across baking channels?

5. How do upload frequency patterns differ across channels, and what do they reveal about each creator’s content strategy?

6. What upload days are most common among top baking channels, and does timing reflect a strategic publishing pattern?

7. How do top baking channels compare in video quality and accessibility features, and what does this reveal about production priorities?

### Data Source and API Access

All data was collected using the **YouTube Data API v3** (https://developers.google.com/youtube/v3). The collection process involved three stages:

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

The dataset spans **14.5 years** from April 2011 to October 2025, providing a comprehensive view of how baking content has evolved on YouTube. Key statistics include:

- **Average views per video**: 1,256,287 (median: 224,350, indicating right-skewed distribution)
- **Average engagement rate**: 3.39% (combining likes and comments as percentage of views)
- **Average video duration**: 7.6 minutes
- **HD adoption**: 99.8% of videos (reflecting industry-wide shift to HD)
- **Caption availability**: 38.8% of videos (lower than expected for accessibility)

The big difference between mean and median views (1.26M vs 224K) indicates that most videos receive moderate viewership, but a small number of viral videos achieve extremely high view counts, pulling the average upward.

## 2. Research Questions

### Which channel demonstrates the strongest overall performance, and how does audience scale affect content efficiency?

Figure 1 displays that Rosanna Pansino leads both in scale (14.8 M subs, 5 B views) and average views per video (≈ 2.7 M). Preppy Kitchen, while smaller (5.7 M subs, 0.8 B views), still achieves strong mid-tier performance — around 0.6 M views per video, which is solid relative to its size and consistent publishing.

- **Audience Scale Effect:** Rosanna’s long-term presence and entertainment-style content generate far broader reach.
- **Steady Engagement:** Preppy Kitchen’s tutorial-driven content performs consistently and maintains healthy engagement despite lower reach.

Subscriber count and total views still matter for absolute performance, but Preppy Kitchen shows that a focused, educational format can sustain strong relative engagement even without celebrity-level scale.

### What is the optimal video duration for maximizing engagement?

Figure 3 shows that videos between 5–15 minutes achieve the highest average view counts, with both the 5–10 minute and 10–15 minute categories performing nearly equally well (≈ 1.7 million views on average). Very short videos (< 5 minutes) and long-form content (> 30 minutes) receive considerably fewer views, suggesting that mid-length videos are the most effective for audience engagement.

These patterns align with YouTube’s algorithmic incentives, which reward videos that balance depth with sustained watch time. Baking tutorials that fall within the 5–15 minute range tend to maximize both retention and educational value, providing a digestible yet complete viewing experience.

### Does audience size significantly influence engagement efficiency across top baking channels?

The scatter plot in Figure 4 reveals a near-perfect positive relationship between views and likes, meaning audience response scales consistently with exposure. However, average engagement rates remain tightly grouped — from 3.2% to 3.6% — showing that larger channels like Rosanna Pansino and smaller ones like BB Baking achieve comparable per-view interaction levels.

This consistency implies that once creators reach a certain quality and audience alignment, engagement efficiency stabilizes regardless of scale. While large channels benefit from reach, smaller creators compensate with community intimacy and trust, reflected in slightly higher engagement ratios.

For baking content, authenticity and instructional clarity may outweigh production scale in sustaining audience connection. Channels should therefore invest in tone, interaction, and viewer retention strategies rather than solely chasing subscriber volume.

### What relationships exist between video features and engagement performance across baking channels?

Figure 5 shows that views are strongly correlated with likes (0.61) and comments (0.58), confirming that videos with higher reach also generate more audience interaction. However, engagement rate shows a weak negative correlation with views (-0.21), suggesting that smaller or niche channels often achieve higher relative engagement despite lower visibility. Duration, tag count, and description length show mild positive correlations, indicating that longer videos often come with more detailed metadata and tags.

These patterns highlight a distinction between reach and connection. While visibility metrics tend to grow together, engagement rate declines slightly as audience size expands, implying that broader audiences may engage less deeply. Content length and optimization features improve discoverability but not necessarily viewer loyalty.

### How do upload frequency patterns differ across channels, and what do they reveal about each creator’s content strategy?

The upload frequency graph (Figure 6) shows distinct long-term publishing strategies across the four baking channels. Rosanna Pansino exhibits the most variable and intensive upload schedule in recent years, with noticeable spikes exceeding 40–50 videos per month around 2023–2024. In contrast, Preppy Kitchen and Bigger Bolder Baking maintain steady, moderate frequencies, while Cupcake Jemma shows more irregular posting intervals with extended gaps.

Publishing consistency strongly correlates with sustained engagement. Channels like Preppy Kitchen show that maintaining a predictable rhythm of high-quality uploads builds long-term viewer trust, while aggressive posting (Rosanna Pansino) boosts visibility but may strain content quality. The most successful strategy appears to be balancing frequency with production value, aligning upload schedules with both audience demand and creator capacity.

### What upload days are most common among top baking channels, and does timing reflect a strategic publishing pattern?

As Figure 7 shows, uploads peak on Thursdays (1,799 videos), with additional surges on Tuesdays (1,073) and Saturdays (908). The lowest publishing days are Fridays (332) and Sundays (259), suggesting that creators intentionally avoid weekends for new releases.

This midweek concentration likely reflects audience behavior and platform optimization. YouTube’s engagement metrics typically rise midweek as audiences return to regular viewing routines. Thursday releases also position videos for stronger weekend momentum, allowing algorithms to accumulate engagement before viewership peaks.

Successful creators appear to time uploads strategically, prioritizing discoverability and algorithmic traction over convenience. For baking channels, consistency in weekday uploads — especially midweek — may contribute more to sustained reach than experimenting with weekend drops.

### How do top baking channels compare in video quality and accessibility features, and what does this reveal about production priorities?

Figure 8 shows that all four baking channels predominantly upload in HD quality, indicating a baseline standard of professional video production. Rosanna Pansino leads in total HD uploads, while Bigger Bolder Baking and Preppy Kitchen stand out for higher caption inclusion rates.

High-quality visuals are essential for recipe-based content, where clarity of technique drives viewer satisfaction. The near-universal shift to HD reflects industry norms, but caption usage highlights an emerging gap — not all creators prioritize accessibility equally. Channels like CupcakeJemma, which show fewer captioned videos, may lose engagement from global or hearing-impaired audiences.

Investing in accessibility features such as captions can enhance reach and viewer inclusivity, particularly for tutorial-heavy genres. As visual quality plateaus across creators, accessibility may become the next differentiator in audience retention and brand perception.


