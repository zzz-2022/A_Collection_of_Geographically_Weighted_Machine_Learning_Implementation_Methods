# Geographically Weighted Machine Learning: Implementation Resources

> **Note**: This is a curated collection of open-source implementations for geographically weighted machine learning models. This list is compiled for **reference and research purposes only**. All intellectual property rights belong to the original authors. Please respect their copyrights and cite the respective papers when using these resources.

> In geographic data research, Geographically Weighted Regression (GWR) is the most widely used spatial modeling method. While it effectively accounts for **spatial heterogeneity**, its reliance on **linear assumptions** limits its ability to capture complex **non-linear relationships** among variables. Consequently, some researchers have turned to non-linear machine learning models. However, standard machine learning models operate as **global regressions** and are often criticized for their lack of **interpretability**. Therefore, combining the strengths of spatial heterogeneity and non-linear modeling offers a promising approach to enhance both the **predictive power** and **explanatory capability** of models. Geographically Weighted Machine Learning modeling provides a valuable framework to address these challenges.

## Overview
This table summarizes available tools and scripts that implement geographically weighted machine learning models, which integrate **spatial heterogeneity and non-linearity**. It focuses on their implementation characteristics and model interpretability capabilities.
| Package / Script Name | Models Implemented | Source | Implementation | Key Notes & Interpretation Methods | Reference Papers |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **SpatialML** | Geographically Weighted Random Forest (GWRF) | [CRAN](https://cran.r-universe.dev/SpatialML) | R Package | Widely applied in research. | Georganos S, Grippa T, Niang Gadiaga A, et al. Geographical random forests: a spatial extension of the random forest algorithm to address spatial heterogeneity in remote sensing and population modelling[J]. Geocarto International, 2021, 36(2): 121-136. |
| **PyGRF** | Geographically Weighted Random Forest (GWRF) | [GitHub](https://github.com/geoai-lab/PyGRF) | Python Package | A mature implementation. Provides local feature importance, but cannot output partial dependence plots (PDP). | Sun K, Zhou R Z, Kim J, et al. PyGRF: An improved Python Geographical Random Forest model and case studies in public health and natural disasters[J]. Transactions in GIS, 2024, 28(7): 2476-2491. |
| **XGeoML** | GWR + scikit-learn model | [GitHub](https://github.com/UrbanGISer/XGeoML) | Python Package | Designed to be comprehensive (offers SHAP, LIME, feature importance). | Liu L. An ensemble framework for explainable geospatial machine learning models[J]. International Journal of Applied Earth Observation and Geoinformation, 2024, 132: 104036. |
| **GeoShapley** | Algorithm for geographical interpretation of ML models | [GitHub](https://github.com/Ziqi-Li/geoshapley) | Python Package | Provides a game-theory based method (extending SHAP) for spatial effect interpretation. | Li Z. Extracting spatial effects from machine learning model using local interpretation method: An example of SHAP and XGBoost[J]. Computers, Environment and Urban Systems, 2022, 96: 101845.<br>Li Z. GeoShapley: A game theory approach to measuring spatial effects in machine learning models[J]. Annals of the American Association of Geographers, 2024, 114(7): 1365-1385. |
| **geoxgboost** | Geographical-XGBoost | [Docs](https://geoxgboost.readthedocs.io/en/latest/#) | Python Package | Provides **local feature importance**. Does **not** provide partial dependence plots. | Grekousis G. Geographical-XGBoost: a new ensemble model for spatially local regression based on gradient-boosted trees[J]. Journal of Geographical Systems, 2025: 1-27. https://doi.org/10.1007/s10109-025-00465-4 |
| **GALAX** | A framework leveraging AutoML & XAI | [GitHub](https://github.com/Pingping9/GALAX-aaag) | Python Package | Provides **local feature importance** (via SHAP). Does **not** provide partial dependence plots. | Wang P, Yuan Y, Li L, et al. GALAX: A Framework for Geospatial Analysis Leveraging AutoML and eXplainable AI[J]. Annals of the American Association of Geographers, 2025: 1-27. |
| — | GW-ML (Random Forest, XGBoost, LightGBM) | [GitHub](https://github.com/UCFLeiHan/Spatial-ML) | Python Scripts | Detailed Jupyter notebooks. Uses **SHAP** for model interpretation, providing **global & local** explanations. | Han, L., & Abdel-Aty, M. Intersection crash analysis considering longitudinal and lateral risky driving behavior from connected vehicle data: A spatial machine learning approach[J]. Accident Analysis & Prevention, 2025, 220, 108180. https://doi.org/10.1016/j.aap.2025.108180 |
| — | Multiscale Geographical Random Forest (MGRF) | [GitHub](https://github.com/PengfeiCui99/Multiscale_Geographical_Random_Forest_MGRF) | Python Scripts | Detailed Jupyter notebooks. Uses **SHAP** for model interpretation, providing **global & local** explanations. | Cui P, Abdel-Aty M, Han L, et al. Multiscale geographical random forest: A novel spatial ML approach for traffic safety modeling integrating street-view semantic visual features[J]. Transportation Research Part C: Emerging Technologies, 2025, 179: 105299. |
| — | Mixed Geographically Weighted XGBoost (M-GWXGB) | [GitHub](https://github.com/yiloufengyue/M-GWXGB) | Python Scripts | Detailed Jupyter notebooks. Uses **SHAP** for model interpretation. | Gao F, He S Y, Kwan M P. Mixed Geographically Weighted XGBoost (M-GWXGB) Model: A New Spatially Explicit Machine Learning Model[J]. Annals of the American Association of Geographers, 2025: 1-32. |
| — | GW-GBDT Model | [Project Page](https://shijiahao998.github.io/NYCBikeShairing/) | R Scripts | Detailed examples. Provides **local feature importance** and **ALE plots**. | Yang H, Shi J, Tao T. Where do built environment attributes most effectively influence bike sharing usage?[J]. Transportation Research Part D: Transport and Environment, 2025, 143: 104717. |
| — | Geographically Weighted Random Forest (GWRF) | [GitHub](https://github.com/cecil8503/GWRF) | Python Scripts | Provides feature importance. Lacks PDP and similar interpretability methods. | Zhang Y, Ge J, Wang S, et al. Optimizing urban green space configurations for enhanced heat island mitigation: A geographically weighted machine learning approach[J]. Sustainable Cities and Society, 2025, 119: 106087. |
| — | GWRBoost | [arXiv](https://arxiv.org/abs/2212.05814) | Python Scripts | Primarily a prediction model. | Wang H, Huang Z, Yin G, et al. Gwrboost: a geographically weighted gradient boosting method for explainable quantification of spatially-varying relationships[J]. arXiv preprint arXiv:2212.05814, 2022. |

## Research Log

Based on literature review:

1.  **Prevalent Tools**: The majority of the reviewed studies implemented the Geographically Weighted Random Forest (GWRF) model using the **R package `SpatialML`**, often integrating it with the **`SHAP`** package for model interpretation. A subset of research has adopted the **`GeoShapley`** library and the **`PyGRF`** library.

2.  **Gap in Interpretation**: While some implementations provide **local feature importance** analysis, detailed explanations regarding **non-linear** and **threshold effects**—often visualized through methods like **Partial Dependence Plots (PDP)**—are generally not explicitly provided. A potential approach to bridge this gap is to calculate PDPs or SHAP values **for each local model** and then aggregate (e.g., average) these local results to derive global insights.

> **Disclaimer**: The above points are based on my personal understanding of the current literature and are provided for reference only. Corrections and discussions are warmly welcomed.

## **⚠️ Disclaimer & Purpose**
> This repository is a **curated, non-commercial collection** compiled for **academic research and reference purposes only**. All copyrights of the original software, code, and publications belong to their respective authors and owners.
>
> - This list only contains **metadata, links, and personal summaries** of publicly available resources.
> - **No original code or data from the referenced projects is redistributed here.**
> - Please always refer to the original source (links provided) for software use and download.
> - If you are an author and believe any content should be modified or removed, please kindly open an Issue.

## Acknowledgment

We extend our sincere gratitude to all the authors and contributors of the open-source projects, packages, and research papers listed in this catalog. Their invaluable work forms the foundation of this curated resource.

