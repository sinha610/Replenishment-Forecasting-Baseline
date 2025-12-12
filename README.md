# Replenishment-Forecasting-Baseline

This project builds a simple, interpretable, and trend-adjusted baseline forecasting model using historical daily outbound demand data from a distribution center. The goal is to support replenishment planning by providing a stable forecast that captures short-term behavior, long-term trend, and yearly seasonality.

1. Business Context

Distribution centers need reliable demand visibility to plan shipments, manage workload, and maintain adequate inventory flow. Even small forecasting errors can lead to stockouts, excess inventory, or unnecessary transportation cost.

This project reconstructs a baseline forecasting method used in large supply-chain organizations (e.g., Adidas) to understand expected daily demand and support replenishment decisions.

2. Problem Statement

The objective is to build a simple baseline demand forecast using historical daily outbound demand data from a distribution center. The company wants a forecasting method that captures year-over-year seasonal patterns, short-term demand behavior, and underlying trends. This baseline will support replenishment planning by providing a stable and explainable starting point that planners can refine based on products or business events.

Note:
The dataset contains a value-based demand signal (stock × price). Unit-level data is unavailable, so forecasts are generated on the value signal as a proxy for physical demand movement.

3. Objectives
Forecasting Objective

Generate daily, weekly, and monthly baseline forecasts using historical demand data.

Pattern-Capturing Objective

The model should capture:

Recent demand behavior (short-term shifts)

Year-over-year seasonality

Underlying long-term trends

A stable signal that avoids reacting to noise

Practical Business Objective

Provide a reliable baseline that planners can use for:

Shipment scheduling

Warehouse workload estimation

High-level replenishment decisions

4. Methodology Overview

The forecasting logic follows a YoY trend-adjusted baseline approach:

Compute demand averages from specific windows ~350–388 days ago

Compute recent 15-day demand average

Estimate Trend Factor = Forward Avg / Backward Avg

Adjust recent demand using the trend factor

Apply optional modifiers:

Holiday factor

Promo factor

Event factor

Weekday factor

This approach blends:

Seasonal similarity

Long-term growth/decline

Recent momentum

Business context adjustments
