# 🥗 Food Startup: User Behavior & A/A/B Testing

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![Pandas](https://img.shields.io/badge/Library-Pandas-150458.svg)
![SciPy](https://img.shields.io/badge/Stats-SciPy-red.svg)
![Plotly](https://img.shields.io/badge/Viz-Plotly-3f4f75.svg)
![Status](https://img.shields.io/badge/Status-Completed-success.svg)

## 📖 Project Overview
I work as a Data Analyst for a startup that sells food products via a mobile app. The design team wants to change the fonts across the entire app to a modern style, but management is worried that the new design might be intimidating to users.

To make a data-driven decision, we conducted an **A/A/B Test**.
* **Goal 1:** Analyze the sales funnel to understand how users navigate from the main screen to purchase.
* **Goal 2:** Evaluate the results of the experiment to determine if the new fonts affect conversion rates.

## 📂 Data Description
The dataset `logs_exp_us.csv` contains user interaction logs with the following columns:
* `EventName`: Type of action (e.g., "MainScreenAppear", "PaymentScreenSuccessful").
* `DeviceIDHash`: Unique user identifier.
* `EventTimestamp`: Date and time of the event.
* `ExpId`: Experiment group ID.
    * `246`: Control Group A1 (Old Fonts)
    * `247`: Control Group A2 (Old Fonts)
    * `248`: Test Group B (New Fonts)

## 🛠️ Methodology
**Tools:** Python, Pandas, Matplotlib/Seaborn, Plotly (for Funnels), SciPy (Z-test).

### 1. Data Preprocessing
* Renamed columns to snake_case.
* Filtered out incomplete data (old logs) to ensure a consistent timeline.
* Verified that there is no overlap of users between groups.

### 2. Event Funnel Analysis
I reconstructed the user journey to calculate conversion rates at each stage:
`Main Screen` → `Offers Screen` → `Cart` → `Payment Successful`.
* Identified the stage with the highest drop-off rate.
* Calculated the overall conversion rate from first visit to purchase.

### 3. A/A/B Experiment Analysis (Hypothesis Testing)
* **A/A Test:** Compared Control Group 246 vs. 247 to ensure the splitting mechanism worked correctly and there were no statistically significant differences between them.
* **A/B Test:** Compared the Test Group (248) against each Control Group (and the combined Control Group) for every stage of the funnel.
* **Statistical Test:** Used the **Z-test for Proportions** (Difference of population proportions).
* **Significance Level (Alpha):** Adjusted to account for multiple comparisons (Bonferroni correction or standard 0.05/0.01 depending on your choice).

## 💡 Key Findings
> *Based on the analysis of the experiment:*

* **Funnel Bottleneck:** The sharpest drop-off occurs at the `[Insertar etapa, ej: Offers Screen]` stage, where we lose `[Insertar %]` of users.
* **Overall Conversion:** Only `[Insertar %]` of users complete the journey from the main screen to payment.
* **A/A Test Results:** No significant difference was found between groups 246 and 247 (p-value > alpha), confirming the accuracy of the testing system.
* **A/B Test Results:** The change in fonts **did not result in a statistically significant difference** in conversion rates for any of the funnel stages.

## 🚀 Conclusions & Recommendations
1.  **Design Decision:** The new fonts **do not negatively impact** user behavior. Management can proceed with the design update if they prefer the new aesthetic.
2.  **Focus Area:** Instead of fonts, the product team should focus on optimizing the `[Etapa con más caída]` stage, as this is where the majority of potential customers are lost.

## 💻 How to Run
  Clone the repository:
    ```bash
    git clone (https://github.com/Kshadow098/12.StarUpFoodService.git)
    ```

    jupyter notebook "Food_App_AB_Test.ipynb"
    ```

---
*Author: Maximiliano* | 
