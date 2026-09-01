# Gaming Analytics: Player Segmentation – KNIME

## Overview
This KNIME workflow segments 40,034 players into 3 distinct behavioral clusters — **Minnows, Dolphins, and Whales** — based on playtime, session frequency, engagement level, achievements, and in-game purchase behavior. Built as part of DA3131 - Data Mining coursework, the project translates clustering results into actionable retention and monetization strategies for game developers and marketers.

## Problem Statement
Segment game players based on behavioral and engagement patterns (playtime, sessions, purchases, achievements, levels) to uncover distinct player types — enabling targeted engagement, personalized experiences, optimized content, and retention strategies.

## Dataset
- **40,034 player records**, 13 features, no missing values, no outliers
- **Demographics:** Age, Gender, Location
- **Gaming behavior:** PlayTimeHours, SessionsPerWeek, AvgSessionDurationMinutes
- **Progress & engagement:** PlayerLevel, AchievementsUnlocked, EngagementLevel
- **Monetization:** InGamePurchases

## Methodology (KNIME Workflow)
`EDA → Preprocessing (encoding + filtering + scaling) → K-Means Clustering → Cluster Profiling & Validation`

- **EDA:** Box plots and a correlation matrix to inspect feature distributions and relationships across PlayTimeHours, InGamePurchases, SessionsPerWeek, AvgSessionDuration, PlayerLevel, and AchievementsUnlocked.
- **Preprocessing:** Rule Engine (grouped players into teens/young-adult/adult age bands), Category-to-Number encoding for categorical variables (e.g., Game Genre, Engagement Level), Column Filter to retain only relevant numerical features, and Z-score Normalization (mean = 0, SD = 1) to ensure fair clustering across variables of different scales.
- **Model:** K-Means clustering, chosen for being fast and effective on large numeric datasets while grouping players with similar gaming patterns into distinct, interpretable segments.
- **Why K = 3:** Produces three meaningful, business-actionable segments — a balance between granularity and simplicity for decision-making.

## Cluster Profiles

| Cluster | Player Count | Avg. Playtime | In-Game Purchases | Preferred Genre |
|---|---|---|---|---|
| **Dolphins** (Cluster_0) | Medium | High | No | Simulation |
| **Whales** (Cluster_1) | Low | Medium | Yes | Strategy |
| **Minnows** (Cluster_2) | High | High | No | Action |

## Recommendations
- **Whales:** Reward with exclusive strategy content and premium bundles — VIP events, rare items, high-value packages.
- **Dolphins:** Retain with immersive content and light purchase offers — retention campaigns, promote simulation titles.
- **Minnows:** Engage with fast, fun gameplay and free rewards — casual action games, short/exciting sessions.

## Features
- Player segmentation using K-Means clustering
- Behavioral and engagement pattern detection across 40K+ players
- Data preprocessing pipeline (encoding, filtering, normalization) built entirely in KNIME
- Cluster profiling translated into genre- and spend-specific business recommendations
- Fully reproducible workflow in KNIME Analytics Platform

## Tools Used
- KNIME Analytics Platform
- K-Means Clustering
- Data Visualization Nodes (Box Plot, Correlation Matrix)
