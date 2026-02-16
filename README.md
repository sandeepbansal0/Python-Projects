## Not All Users Are Equal: Modeling Incremental Engagement with Uplift AI
<p align="center">
  <img src="https://raw.githubusercontent.com/sandeepbansal0/Python-Projects/main/Images/CustomerEngagement.png" 
       alt="Customer Engagement Banner" 
       width="100%" />
</p>


# 📊 Predicting Behavior Change — Uplift Modeling for Digital Engagement

## Executive Summary

Traditional engagement models predict who is likely to click or complete an article.  
This project goes further — it estimates who can be influenced.

Using behavioral session data across multiple news domains, I built a causal uplift modeling framework to measure the incremental impact of short-form video exposure on article completion.

**Objective**

> Identify users who become more likely to engage when exposed to video — not just those already likely to engage.

---

## 🎯 Business Problem

Digital media platforms often deploy engagement features (e.g., embedded video) uniformly.

However:

- Some users are already highly engaged (no intervention needed)
- Some users are unlikely to engage regardless of treatment
- Only a subset of users are “persuadable”

Without causal modeling, personalization efforts waste resources and dilute ROI.

This project answers:

- Who should we target?
- Which content domains respond best to intervention?
- What is the estimated incremental engagement lift?

---

## 🧠 Modeling Approach

### 1️⃣ Engagement Scoring

Constructed a composite engagement metric using:

- Scroll depth  
- Time spent  
- Completion flag  
- Secondary interactions (suggested link clicks, video views)  

Users in the top 30% were classified as high-engagement sessions.

---

### 2️⃣ Uplift Modeling (T-Learner Framework)

**Treatment Variable**  
- Watched short video (binary)

**Outcome Variable**  
- Reached bottom of article (completion)

Two separate Random Forest models were trained:

- Model A → Predict engagement probability if video is shown  
- Model B → Predict engagement probability without video  

**Uplift Score per user**

