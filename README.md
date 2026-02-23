# Protecting Children's Digital Privacy: Predicting COPPA Violation Risk in Mobile Applications
## Background
The digital world is increasingly accessible to children, with mobile apps playing a significant role in their entertainment, education, and social interaction. However, this increased access also brings potential risks, particularly regarding the collection and use of children's personal information. The Children's Online Privacy Protection Act (COPPA) in the United States, and similar regulations globally, aim to protect children's privacy online by requiring app developers to obtain parental consent before collecting data from users under 13.

In this competition, the objective is to build a machine learning model capable of predicting whether a mobile application poses a risk of non-compliance with COPPA. By identifying potentially high-risk apps, this project aims to support app stores, developers, and parents in fostering a safer digital environment. The model leverages various application attributes—including app category, download indicators (as a proxy for target audience), privacy policy characteristics, and developer-related information—to estimate the likelihood of COPPA violations.

## Problem Statement
The core objective is a binary classification task:
- Target Variable: coppaRisk (boolean: true or false) 
- Predict whether an app is at risk of violating COPPA, true indicates a higher risk of non-compliance, while false suggests a lower risk.

## Dataset
The dataset contains information scraped from a major app marketplace, along with derived features related to privacy and compliance. It includes a mix of categorical, numerical, and boolean features. Missing values are represented by empty strings.
| Column | Description |
| ------ | ----------- |
| developerCountry | The country where the app developer is registered. This might provide insights into regional privacy law awareness and enforcement. Values like "ADDRESS NOT LISTED IN PLAYSTORE" and "CANNOT IDENTIFY COUNTRY" indicate missing or unretrievable information. |
| countryCode | The target market or region for the app (e.g., GLOBAL, NA, EMEA, LATAM, APAC). NA likely means North America. GLOBAL is a broad category, while others are more geographically specific. |
| userRatingCount | The total number of user ratings the app has received. |
| primaryGenreName | The primary category the app is listed under (e.g., Games, Books & Reference, Education, etc.). |
| Downloads | An approximate range of the number of times the app has been downloaded with format (min-max) (e.g., "100000 - 500000"). |
| deviceType | Indicates the types of devices the app is compatible with (e.g., smartphone, tablet, connected-tv/ott, undetermined). |
| hasPrivacyLink | Whether the app listing includes a link to a privacy policy. The presence of a link is a basic compliance step |
| hasTermsOfServiceLink | Whether the app listing includes a link to terms of service |
| hasTermsOfServiceLinkRating | A rating (e.g., "low", "medium", "high") potentially reflecting the quality or comprehensiveness of the terms of service |
| isCorporateEmailScore | A score (likely between 0 and 100) that might indicate the likelihood that the developer's email address is a corporate email rather than a personal one. A higher score could indicate a more established developer, potentially with better compliance practices |
| adSpent | The amount of money spent on the ads |
| appAge | The age of the app in days (likely since its listing on the app store). Older apps might be less likely to be updated with current privacy best practices |
| averageUserRating | The average user rating of the app (e.g., on a scale of 1 to 5). |
| appContentBrandSafetyRating | A rating (e.g., "low", "medium", "high") that likely reflects the suitability of the app's content for a general audience. This is not directly about privacy, but about content moderation. |
| appDescriptionBrandSafetyRating | (Categorical) Similar to the above, but specifically rates the description of the app, rather than the app itself |
| mfaRating | (Categorical) A rating (e.g., "low", "medium", "high") likely related to Made for Advertising Apps. |
| coppaRisk | The target variable indicates whether or not this application might be at risk of not complying with COPPA. |

## Evaluation
Submissions will be evaluated based on a suitable classification metric, likely:
- AUC, or Area Under the ROC Curve, is a single metric that summarizes the overall effectiveness of a classifier. Its value ranges from 0 to 1, where 0.5 suggests the model performs no better than random guessing, and a value of 1 indicates perfect classification performance.

## Results
The best-performing model in this project achieved an AUC score of 0.8254 (82.54%) on the Kaggle leaderboard test dataset.
