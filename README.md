### Poster and Project Summary
**Background/Motivation**: In an era where climate change's impacts are increasingly tangible, understanding the interplay between public discourse and environmental phenomena is crucial. This study delves into how precipitation anomalies influence public discussions on climate change, leveraging advanced machine learning techniques to uncover patterns and causations that can inform effective communication strategies and policy development.

**Research Questions**:
1. How do precipitation anomalies affect the level of public discourse on climate change?
2. Can we leverage machine learning to predict periods of heightened public discourse on climate change based on weather patterns?

**Application Scenario (Data Source)**: Utilizing a comprehensive dataset from NOAA, this research analyzes US-based precipitation anomalies and correlates them with public interest metrics sourced from Google Trends. The study spans a decade, offering a rich temporal context to understand the evolving climate discourse.

**Methodology**: The study employs a dual-methodological approach:
- A Convolutional Neural Network (CNN) to analyze spatial data for predicting precipitation anomalies.
- Causal inference with Ordinary Least Squares (OLS) Linear Regression to explore the relationship between weather patterns and public discourse, distinguishing between anomalous and non-anomalous periods.

**Results**:
- The CNN model demonstrates a strong capability to predict precipitation anomalies, highlighting a general correlation with public discourse on climate change.
- The OLS regression analysis reveals a nuanced relationship; while extreme weather events do spur more public discourse, the effect varies and is not uniformly significant across all anomalous periods.

**Intellectual Merits**: This research advances the understanding of how environmental changes, particularly extreme weather events, shape public discourse on climate change. By integrating machine learning with traditional statistical analysis, the study offers a novel perspective on predicting and understanding public engagement with climate issues.

**Practical Impacts**: The findings have significant implications for policymakers, climate communicators, and activists. By identifying key periods when the public is most receptive to climate change discussions, stakeholders can tailor communication and policy initiatives to maximize impact and engagement, ultimately fostering a more informed and proactive societal response to climate challenges.

![Poster](https://github.com/Rising-Stars-by-Sunshine/Stats201_Yuanjun_Lin/assets/31695074/71df9d7a-d971-4679-af53-33358b01719a)

### Literature
Recent studies have delved into the intricate relationship between extreme weather events and the ensuing discourse on climate change, employing various methodological approaches to unravel the complexities of public engagement and perception. Notably, the work by Torricelli et al. (2023) provides valuable insights into how hurricanes, a specific kind of extreme weather, shape the climate change discourse on platforms like Twitter. Their analysis, grounded in social media data, underscores the pivotal role such platforms play in amplifying conversations around climate-related phenomena, ultimately influencing the broader narrative on climate change (Torricelli M, et al., 2023).

Similarly, the study on "Event attribution and partisanship shaping local discussion of climate change after extreme weather" ventures into the realm of local discourse triggered by extreme weather events, highlighting the subjective nature of what constitutes "extreme weather" and how it's discussed within local communities (Nature Climate Change, 2019). This research underscores the significant impact of subjective interpretation and human-compiled data on understanding public responses to climate anomalies.

While these studies contribute substantially to our understanding of climate discourse dynamics, they also present a research gap that our current study aims to bridge. Our dataset, derived from official NOAA records, diverges from the aforementioned studies by focusing not on one specific type of extreme weather event, such as hurricanes, but on a broader spectrum of precipitation anomalies. Moreover, our approach departs from the largely qualitative and human-centric analysis methods previously employed. Instead, we leverage an automated, machine-learning-driven process that directly inputs official meteorological data into our models, minimizing subjective interference and allowing for a more objective assessment of the relationship between climate change discussions and precipitation patterns.

This distinction in data source and methodology underscores the novelty of the present study, extending the discourse on climate change communication by introducing a quantitative, data-driven perspective that complements existing qualitative analyses. By doing so, we contribute a new dimension to the ongoing dialogue on how extreme weather events, perceived through the lens of objective meteorological data, influence public discussions on climate change, thereby enriching the collective understanding necessary for effective climate communication and policy development.

### Methodology

#### Research Question Formulation:

- **Objective**: The primary objective of this study is to investigate the relationship between precipitation anomalies (extreme weather patterns) and the level of public interest or discourse on climate change. By understanding this relationship, we aim to provide actionable insights for policymakers on the timing of initiatives to promote climate change awareness and action.

- **Significance**: This question holds critical importance as it directly informs the strategic planning of climate change communication and policy implementation. In an era where climate change impacts are becoming more pronounced, understanding when public interest peaks in response to extreme weather can enable more effective, timely, and resonant policy and awareness campaigns, maximizing their impact and public engagement.

#### Operational Measures:

- **Variables**:
  - **Independent Variable (X)**: Precipitation anomalies, quantified as deviations from long-term precipitation averages, representing extreme weather patterns.
  - **Dependent Variable (Y)**: Public interest or discourse on climate change, measured through metrics such as Google Trends data, social media activity, or other proxies for public engagement and awareness.

- **Data Type**: The dataset is a **time-series** collection, capturing the temporal dynamics between precipitation anomalies and public discourse on climate change over a defined period. This format allows for the analysis of trends, patterns, and potential causality within the data.

#### Hypothesis Development:

- **Prediction Hypothesis**: We hypothesize that significant precipitation anomalies, indicative of extreme weather events, lead to a measurable increase in public interest and discourse on climate change. This relationship is predicated on the assumption that extreme weather events heighten public awareness and concern regarding climate change, thus driving more robust discussions and engagements on the topic.

- **Justification**: The rationale behind this hypothesis stems from the observable trend where extreme weather events often catalyze public and media attention towards climate change, as evidenced by increased news coverage, social media activity, and online searches related to climate change in the aftermath of such events. This pattern suggests a reactive public response to visible and impactful manifestations of climate change, such as extreme weather.

- **Machine Learning Algorithm Selection**: To test this hypothesis, a **Convolutional Neural Network (CNN)** is selected for its prowess in handling and analyzing spatial data. Given the geospatial nature of precipitation data and its complex relationship with public discourse, CNNs are well-suited for capturing the intricate patterns within the data that might influence public interest in climate change. The choice of a CNN is justified by its proven capability to extract meaningful features from complex datasets, making it an ideal tool for this analysis.
In addition to the Convolutional Neural Network (CNN), our study employs **Ordinary Least Squares (OLS) linear regression** within a **causal inference framework** to further elucidate the relationship between precipitation anomalies and public discourse on climate change. This complementary approach enables a counterfactual analysis, distinguishing between months categorized as anomalous and non-anomalous based on precipitation data. By employing OLS linear regression, we aim to quantify the direct impact of extreme weather events on the level of public engagement with climate change issues. This method allows for a more traditional statistical analysis, providing a clear, interpretable model that can highlight potential causal relationships. The distinction between anomalous and non-anomalous months serves as a critical factor in our analysis, enabling us to isolate the effect of extreme weather patterns from the baseline public discourse on climate change. This bifurcation enhances the robustness of our counterfactual analysis, offering nuanced insights into how significant deviations from normal weather conditions may catalyze public discussions and concerns regarding climate change.
This methodology section outlines the foundation of the study, detailing the research objective, the significance of the inquiry, the operational measures for the analysis, and the rationale behind the chosen hypothesis and machine learning algorithm. This structured approach ensures a clear and systematic investigation into the relationship between extreme weather patterns and public discourse on climate change.

### 1.1. The Machine Learning Workflow -CNN

#### Model Development:

**Data Processing**:
The CNN model development commenced with meticulous data processing to ensure the accurate quantification of our variables of interest - precipitation anomalies (independent variable) and public interest in climate change (dependent variable). The preprocessing involved:
- **Normalization**: Scaling the precipitation data to a standard range to facilitate efficient learning by the CNN.
- **Reshaping**: Converting the data into a format compatible with the CNN, specifically into a 4D tensor of shape `[samples, height, width, channels]`, where `height` and `width` correspond to the spatial dimensions of the input data, and `channels` denote the data features, such as precipitation intensity or geographical indicators.
- **Augmentation** (for future robustness improvement): Simulating data using potentially partially real data can be beneficial for improving the robustness of the model. Also, enhancing the dataset through techniques like noising, or translation to increase the diversity of the training set and improve the model's generalization capabilities.
- **Max Pooling**: The spatial resolution of the data is reduced for efficient training and lessening the tendency to overfit.
  
#### Results Presentation:

**Training and Testing**:
- The dataset was partitioned using an **80-20 split** for training and testing, ensuring a comprehensive evaluation of the model's performance on unseen data.
- **5-fold Cross-Validation**: To further validate the model's effectiveness and generalizability, we employed 5-fold cross-validation within the training set. This approach entails dividing the training set into five subsets, using four for training and one for validation in each iteration, thereby ensuring that every data point is used for both training and validation at some stage.

**Data Visualization**:
- **Performance Metrics Over Epochs**: Visuals such as line graphs were employed to depict the model's learning progress over epochs, highlighting trends in accuracy and loss for both training and validation sets.
- **Feature Map Visualizations**: This is only as a glance of potentials in this methodology as the feature maps can be overfitted to the limited samples so it might not fully reflect the true contribution of each region to the discourse intensity. To demystify the CNN's internal workings, we visualized the feature maps generated by the convolutional layers, providing insights into the patterns and features the model was focusing on.
  ![Primitive Low-res Feature Map of Jan 2022] (https://github.com/Rising-Stars-by-Sunshine/Stats201_Yuanjun_Lin/assets/31695074/0c99228e-b045-4594-9734-3db637a1edc0)

- **Comparative Plots**: Scatter plots and line charts comparing the predicted values against the ground truth for the test set, elucidating the model's predictive accuracy and areas of divergence.

#### Model Evaluation:

**Evaluation Criteria**:
- The model's performance was rigorously assessed using metrics pertinent to regression tasks, including **Mean Squared Error (MSE)**, **Root Mean Squared Error (RMSE)**, and **Mean Absolute Error (MAE)**, each offering a different perspective on the model's accuracy and error distribution. However, it should be noticed that the limited sample size make these measurements quite stocastic.

**Iterative Improvement**:
- **Hyperparameter Tuning**: Due to the limited samples, complex tuning can contribute to overfitting so only basic tuning and iterative improvement are adopted. Adjustments to the model's architecture and training parameters, such as the number of layers, filter sizes, learning rate, and batch size, were systematically explored to enhance performance.

### The Machine Learning Workflow - Causal Inference with OLS Linear Regression

#### Model Development:

**Data Processing**:
For the causal inference analysis using Ordinary Least Squares Linear Regression (OLS-LR), a crucial step involved aggregating the precipitation anomaly values across all grid squares to obtain a singular scalar value for each month. This process transformed the inherently multidimensional spatial data into a one-dimensional independent variable (IV), suitable for regression analysis. The steps included:
- **Aggregation**: Summarizing the spatially distributed precipitation anomaly data into a single anomaly index per month, ensuring a concise and manageable dataset for regression analysis.
- **Normalization**: Standardizing the aggregated anomaly indices to align with typical regression analysis prerequisites, facilitating a more stable and interpretable model.

**Anomaly Classification**:
- To distinguish between anomalous and non-anomalous months, the median value of the aggregated anomaly index served as the threshold. Months with an anomaly index above the median were classified as anomalous, whereas those below were considered non-anomalous. This binary classification informed the subsequent regression analysis, allowing for a differentiated examination of public discourse on climate change during periods of varying climatic extremity.

#### Results Presentation:

**Regression Analysis**:
- The OLS-LR model was fitted separately for anomalous and non-anomalous months, with the scalar anomaly index as the independent variable and public interest in climate change as the dependent variable. This bifurcated analysis aimed to discern the differential impact of extreme weather patterns on climate change discourse.

**Data Visualization**:
- **Regression Diagnostics**: Visuals such as residual plots and Q-Q plots were utilized to assess the assumptions of linear regression and diagnose potential model inadequacies.
- **Coefficient Interpretation**: Bar graphs or coefficient plots highlighted the estimated regression coefficients and their confidence intervals, elucidating the magnitude and direction of the relationship between precipitation anomalies and public discourse on climate change.
- **Anomaly Effect Visualization**: Scatter plots with regression lines for anomalous and non-anomalous months separately depicted how the level of public discourse varied in relation to the precipitation anomaly index, offering a clear visual contrast between the two scenarios.

This approach to causal inference with OLS-LR, centered on a methodical data processing strategy and a nuanced analysis framework, provides a rigorous examination of how extreme weather events, as quantified by precipitation anomalies, influence public discussions on climate change. The use of a median-based classification for anomalies ensures a robust analytical foundation, capturing the nuanced impact of climatic extremities on societal discourse.

## Research Findings
![Findings flowchart created using markmap.js](https://github.com/Rising-Stars-by-Sunshine/Stats201_Yuanjun_Lin/assets/31695074/ce593065-8e7e-4f00-b175-f79bd5fe6017)
To effectively communicate the results of your research in the README, it's essential to directly link the outcomes back to each posed research question, elucidating how the employed methodologies provided the answers. Here's a structured approach to presenting these findings:

---

## Results

Our research embarked on a journey to unravel the dynamics between precipitation anomalies and public discourse on climate change, guided by two pivotal research questions. Here's how our findings provide answers to these questions:

### Research Question 1: How do precipitation anomalies influence public discourse on climate change?

**Method: Convolutional Neural Network (CNN)**
- The CNN model, designed to analyze spatial patterns in precipitation data, revealed a general correlation between precipitation anomalies and heightened public interest in climate change. The model's predictive accuracy, especially in non-extreme weather conditions, underscores the sensitivity of public discourse to variations in precipitation patterns.

**Results:**
- The CNN's performance, reflected in its ability to approximate actual precipitation anomalies, indicates a tangible link between observed weather patterns and subsequent public discussions on climate change. However, the model's difficulty in accurately predicting extreme anomalies suggests the influence of additional, unaccounted factors in shaping public discourse during significant weather events.

### Research Question 2: Can we identify periods of heightened climate change discourse based on precipitation anomalies?

**Method: Causal Inference with OLS Linear Regression**
- By aggregating spatial precipitation data into a monthly anomaly index and classifying months as anomalous or non-anomalous based on the median value, the OLS-LR analysis provided a nuanced view of the relationship between extreme weather events and climate change discussions.

**Results:**
- The regression analysis for anomalous months indicated a positive, albeit statistically insignificant, relationship between precipitation anomalies and climate change discussions. This suggests that while extreme weather events may prompt increased public discourse, the complexity of this relationship warrants further investigation.

### Part VII: Future Research Directions

#### Causal Inference Methods

**Background/Motivation**: Building on the current study's exploration of precipitation anomalies and public discourse on climate change, further research could delve deeper into the causal mechanisms underlying this relationship. Understanding these causal links is crucial for devising targeted, effective climate communication strategies and policies.

**Research Questions**: How do specific types of precipitation anomalies (e.g., extreme rainfall, droughts) causally impact the nature and intensity of climate change discourse? Which external factors (e.g., media coverage, political events) mediate or moderate this relationship?

**Methods**: Future studies could employ advanced causal inference methods such as **Instrumental Variables (IV) analysis** or **Propensity Score Matching (PSM)** to address potential endogeneity issues and uncover the true causal effects. For IV analysis, identifying an appropriate instrument that affects precipitation anomalies but not directly the climate change discourse would be key. For PSM, matching observations with similar characteristics except for the anomaly occurrence could help isolate its causal impact.

- **Potential Results**: This approach could reveal nuanced insights into how different types of weather anomalies influence public discussions on climate change, accounting for confounding factors and biases.
  
- **Contributions**: Such research would contribute significantly to the climate communication literature by providing empirically grounded insights into how to effectively engage the public on climate issues, especially during extreme weather events.

**Causal Graph Illustration**:
```
[Extreme Weather Events (Treatment)] --> [Public Discourse on Climate Change (Target)]
  ↑                                               ↑
[Media Coverage, Political Events (Confounding Variables)]
```

#### Optimization Methods

**Background/Motivation**: Optimizing the timing and content of climate communication efforts can maximize their impact. By understanding the dynamics of public engagement with climate discourse, particularly in response to weather anomalies, policymakers can more effectively allocate resources and strategize outreach efforts.

**Research Questions**: What are the optimal strategies for initiating climate change communication in response to different precipitation anomalies to maximize public engagement and policy impact?

**Methods**: Utilizing **Reinforcement Learning (RL)** algorithms could offer a novel approach to this challenge. By framing the problem within an RL framework, where the state represents the current climate and public discourse conditions, the action encompasses different communication strategies, and the reward is based on the level of public engagement or policy adoption, we can iteratively identify optimal communication strategies.

- **Potential Results**: This method could identify the most effective timing and methods for climate change communication in relation to various weather patterns, enhancing public awareness and action.
  
- **Contributions**: Implementing RL in climate communication research could pioneer a data-driven approach to environmental policy and advocacy, tailoring efforts to real-time conditions and maximizing their societal impact.

**Reinforcement Learning Framework Illustration**:
```
[State (Current Climate Conditions, Public Discourse Levels)]
     ↓ (Action: Communication Strategy)
[Public Engagement (Reward)]
```
These future research directions aim to harness the power of causal inference and optimization methods to advance our understanding of climate change communication's dynamics, ultimately contributing to more effective public engagement and policy development in response to climate anomalies.

### Acknowledgement
I hereby extend my heartfelt gratitude to Professor Luyao Zhang for her invaluable guidance, insightful critiques, and unwavering support throughout the course of this research. Especially in terms of organizing all the activities, workshops, and symposiums besides the regular lectures which have significantly facilitated the progress of this study. During these events and activities, my fellow classmates have been professional and helpful, providing constructive suggestions and a harmonic, hospitable, and decent academic environment. Here just to name a few, including Aida Camacho Ponce de Leon for her devotion to organize group discussion and reciprocally beneficial study environment; Pengyu Chen for his insightful suggestions on the draft; Jiahe Qian for his engagement in the group and as a collective learning group leader.

### References
Torricelli M, Falkenberg M, Galeazzi A, Zollo F, Quattrociocchi W, et al. (2023) How does extreme weather impact the climate change discourse? Insights from the Twitter discussion on hurricanes. PLOS Climate 2(11): e0000277. https://doi.org/10.1371/journal.pclm.0000277. Retrieved at https://journals.plos.org/climate/article/citation?id=10.1371/journal.pclm.0000277.

Nature Climate Change (2019). Event attribution and partisanship shape local discussion of climate change after extreme weather. 
