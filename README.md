[![DOI](https://zenodo.org/badge/1108465203.svg)](https://doi.org/10.5281/zenodo.17791439)

# Explaining-Household-Access-to-Heavy-Rail-Services-Using-Interpretable-Machine-Learning
ML models (RF, SVM, KNN, XGBoost) predict household heavy rail access using NHTS 2022 data. After preprocessing and 5 fold tuning, models reach about 96 percent accuracy. SHAP shows proximity to stations, vehicle availability, and urban density as key drivers, giving interpretable insights for transport policy.

# Methodology
<p align="center">
<img src="images/methodology_overview.jpg" align="center" width="75%"/>
</p>

# Result
Four ML models were evaluated for predicting travel mode choice. Ensemble models clearly outperformed simpler classifiers. Random Forest achieved the highest accuracy at 96.46 percent, closely followed by XGBoost at 96.13 percent, both showing stable cross validation performance. KNN performed moderately, and SVM showed the weakest generalization.

| Model         | Accuracy | Macro F1 | Mean CV Score | CV Std Dev |
|---------------|----------|---------|---------------|----------|
| KNN           | 0.8199   | 0.58    | 0.7906        | 0.0050   |
| SVM           | 0.6439   | 0.59    | 0.6331        | 0.0424   |
| XGBoost       | 0.9613   | 0.94    | 0.9560        | 0.0040   |
| Random Forest  | 0.9646   | 0.95    | 0.9587        | 0.0065   |

**Feature Importance Analysis via SHAP**

SHAP analysis identified URBANSIZE, CENSUS_D, CENSUS_R, and other urbanization metrics as the strongest predictors. Socioeconomic variables like household income and age also contributed meaningfully, while WORKER and passenger or driver flags had minimal impact. Overall, ensemble models delivered superior accuracy and interpretability, with urban structure emerging as the dominant factor shaping travel mode choice.

<table>
  <tr>
    <td align="center">
      <img src="images/MSA_with_Heavy_Rail_Access_bar.png" width="90%"><br>
      <em>SHAP Bar plot for MSA with Heavy Rail Access</em>
    </td>
    <td align="center">
      <img src="images/MSA_without_Heavy_Rail_Access_bar.png" width="90%"><br>
      <em>SHAP Bar plot for MSA without Heavy Rail Access</em>
    </td>
  </tr>
</table>

<table>
  <tr>
    <td align="center">
      <img src="images/MSA_with_Heavy_Rail_Access_beeswarm.png" width="90%"><br>
      <em>SHAP Beeswarm plot for MSA with Heavy Rail Access</em>
    </td>
    <td align="center">
      <img src="images/MSA_without_Heavy_Rail_Access_beeswarm.png" width="90%"><br>
      <em>SHAP Beeswarm plot for MSA without Heavy Rail Access</em>
    </td>
  </tr>
</table>

**Dependency plot**

