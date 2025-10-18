[← Back to Module 3](../modules/module-3/index.md)

# Unit 6 – Team Project: Airbnb Price Prediction and Market Segmentation in New York City

This team project applied machine-learning techniques to the **AB_NYC_2019 dataset** to analyse what drives Airbnb rental prices and how listings can be grouped into meaningful market segments.  
Our aim was to identify the key predictors of nightly price and explore how **predictive modelling (linear regression, random forest)** and **unsupervised clustering** could together support Airbnb’s pricing and marketing strategy.

The project developed essential teamwork, data-analysis, and communication skills, forming the foundation for the more advanced individual project completed in Unit 11.

---

## Project Overview

### Objectives
- Identify which features most strongly influence nightly price for Airbnb listings in New York City.
- Build regression and ensemble models to quantify and predict price variation.
- Apply **k-means clustering** to reveal natural market segments based on listing type, location, and availability.
- Combine predictive and segmentation insights to inform strategic decisions for hosts and Airbnb itself.

### Tools and Methods
- **Dataset:** *Inside Airbnb (2019)*, ~48 000 listings across five boroughs.
- **Languages / Tools:** Python (Jupyter Notebook) and Matplotlib/Seaborn for visualisation.
- **Collaboration Tools:** Discord, Google Drive, Zoom.
- **Pre-processing:** Removal of extreme outliers (e.g., multi-year minimum stays), imputation of missing review counts, one-hot encoding, and log transformation of the target variable.
- **Algorithms:**
    - *Linear Regression* — baseline for interpretability.
    - *Random Forest Regressor* — captured non-linear effects and produced feature-importance rankings.
    - *K-Means Clustering* — identified three distinct market segments.

---

## My Individual Contributions

Within the team, my main contributions were:

- **Random Forest Modelling**
    - Implemented and fine-tuned the **Random Forest Regressor**, testing both unlogged and log-transformed targets.
    - Evaluated model performance using R² and MAE and produced the **feature-importance** and **actual vs predicted** graphs used in the final report (Figures 2 & 3).

- **Support with Clustering**
    - Worked closely with **Amaka** on the **k-means clustering** stage, ensuring correct preprocessing, variable selection, and validation of the three-cluster solution.
    - Reviewed plots and results to confirm that segmentation patterns aligned with the regression insights.

- **Report Writing and Visualisation**
    - Wrote the **Introduction** and **Conclusion** sections of the report.
    - Designed several key **graphs and figures**, ensuring consistency in formatting and captions across the final submission.
    - Contributed feedback on the integration of all analytical sections for clarity and flow.

- **Collaboration and Coordination**
    - Attended all meetings, helped merge contributions, and ensured visual outputs were delivered on time for submission.

**Evidence of my work**  
Figures and written sections corresponding to my contributions are included in the final submitted report and corroborated by the peer-evaluation record.

---

## Key Results

| Model | Description | R² Score | MAE ($) | Observations |
|--------|--------------|-----------|-----------|---------------|
| **Linear Regression (log-target)** | Transparent baseline model | ≈ 0.52 (0.33 unlogged) | 48.6 | Clear identification of room type & location as dominant drivers. |
| **Random Forest Regressor (log-target)** | Non-linear ensemble model | ≈ 0.43 | 46.5 | Slightly higher accuracy; captured complex feature interactions. |
| **K-Means Clustering (k = 3)** | Unsupervised segmentation | – | – | Defined three market tiers – premium (Manhattan entire homes), mid-market, and budget listings. |

**Interpretation**
- *Room type* and *neighbourhood group* were the strongest determinants of nightly price.
- Random Forest modestly improved predictive accuracy but primarily added interpretive value via feature importance.
- Clustering revealed clear market tiers, complementing the regression findings and supporting Airbnb’s differentiated pricing strategy.

---

## Team Dynamics and Peer Evaluation

According to my self-evaluation:
- I consistently attended meetings, took initiative, and ensured progress toward deadlines.
- My main strengths were **leadership, coordination, and responsibility** for integrating final outputs.
- Challenges included **over-commitment** near the submission deadline, where I carried a disproportionate editing load, something I plan to address in future collaborations by delegating more evenly.

Three of six team members (myself, Viktor, and Amaka) contributed actively throughout.  
The fourth joined late and participated minimally, which created additional pressure in the final week.  
Despite this, the team functioned cooperatively, and communication remained positive and solution-oriented.

The project achieved a mark of 72 % (Distinction).

Feedback praised the clarity of the modelling pipeline, quality of visualisations, and practical relevance, noting that stronger critical analysis of model limitations and validation metrics (e.g., silhouette score) could further improve the work.

---

## Mini-Reflection

This collaborative project enhanced my understanding of:
- Balancing **interpretability** and **predictive power** in regression vs. ensemble models.
- The value of **clustering** for translating technical findings into actionable business insight.
- The importance of **leadership balance** - contributing strongly while empowering others.

These lessons informed my independent Unit 11 project, where I applied the same approach of preprocessing, validation, and reflective analysis to a deep-learning context.

---

## Artefacts and Supporting Evidence

-  [Final Team Submission – *Airbnb Price Prediction and Segmentation in New York City* (PDF)](project-report.pdf)
-  [Team Meeting Notes – Week 4 (PDF)](../artefacts/module-3/unit-4-meeting-notes.pdf)
-  [Team Meeting Notes – Week 6 (PDF)](../artefacts/module-3/unit-6-meeting-notes.pdf)

**Group Grade:** 72 % (Distinction)  
**Final Individual Score:** 86 % (Distinction)

*Peer evaluation and detailed feedback are referenced privately but not publicly shared to protect confidentiality.*

