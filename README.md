# Renewed iPhones Complaint Analysis: Uncovering Key Customer Pain Points

## 🚀 Project Overview

This project aims to identify and analyze the primary complaint drivers for renewed iPhones based on customer review data. By transforming raw, unstructured text reviews into actionable insights, this analysis helps pinpoint specific issues related to different iPhone models, enabling targeted improvements for product management, quality control, and customer satisfaction. The project encompasses data extraction, robust preprocessing, exploratory data analysis (EDA), and interactive dashboard visualization.

## ✨ Key Features

* **Automated Review Extraction:** Efficiently gathers customer reviews.
* **Comprehensive Data Preprocessing:** Handles missing values, text cleaning, sentiment analysis, and feature engineering.
* **Complaint Topic Modeling:** Identifies recurring themes and categories of complaints.
* **Interactive Dashboard:** Provides a dynamic platform for stakeholders to explore complaint trends across models and time.
* **Actionable Insights:** Pinpoints specific models and complaint types requiring attention.

## 📺 Project Demo & Live Access

* **Demo Video:** [Click here to watch a demo of the interactive dashboard.](YOUR_DEMO_VIDEO_LINK_HERE)

## 📈 Dashboard Preview

Here's an overview of the interactive Tableau dashboard, showcasing the distribution of star ratings, complaint types, and trends over time:

![Overall Dashboard View](images/dashboard_overview.png)

## 💡 Interactive Exploration

The dashboard is designed for dynamic exploration. Clicking on a specific iPhone model (e.g., iPhone 12 Pro Max, iPhone 13, iPhone 14 Pro) highlights its specific complaint profile across all relevant charts.

* **iPhone 12 Pro Max Complaint Profile:**
    ![Dashboard Filtered by iPhone 12 Pro Max](images/dashboard_iphone_12_pro_max_filter.png)

* **iPhone 13 Complaint Profile:**
    ![Dashboard Filtered by iPhone 13](images/dashboard_iphone_13_filter.png)

* **iPhone 14 Pro Complaint Profile:**
    ![Dashboard Filtered by iPhone 14 Pro](images/dashboard_iphone_14_pro_filter.png)

## 🛠️ Project Flow & Methodology

The project followed a structured data science methodology:

### 1. Data Extraction & Collection

* Customer reviews for renewed iPhones were sourced from relevant platforms (e.g., e-commerce sites, tech forums).
* An automated script (details in the `clean_code.ipynb` notebook) was used to systematically extract review text, star ratings, and associated metadata.

### 2. Data Preprocessing & Cleaning (`clean_code.ipynb` & `final.ipynb`)

This crucial phase transformed raw, unstructured data into a clean, analysis-ready format.

* **Handling Missing Values:** Identification and appropriate treatment of any missing data points to ensure data integrity.
* **Text Normalization:** Lowercasing, removal of punctuation, special characters, and numbers from review text to standardize the data.
* **Stop Word Removal:** Elimination of common words (e.g., "the", "a", "is") that do not contribute to meaningful insights.
* **Lemmatization/Stemming:** Reducing words to their base form to aggregate similar terms.
* **Sentiment Analysis:** Applying a sentiment model to quantify the emotional tone (positive, negative, neutral) of each review, providing a numerical 'Sentiment Score' and 'Negative Sentiment Rate'.
    ![Sentiment Analysis Output Example](images/notebook_sentiment_analysis_output.png)
    *Description: Screenshot of the DataFrame snippet showing newly added sentiment scores and rates.*
* **Feature Engineering:**
    * **Complaint Topic Extraction:** Using techniques like TF-IDF and clustering (or a predefined dictionary approach) to group similar complaints into distinct "Final Topics" (e.g., Battery Life & Charging, Screen & Cosmetic Condition, Seller & Carrier Unreliability). This was a critical step in turning free-text complaints into categorizable data.
        ![Complaint Topic Extraction Output](images/notebook_topic_extraction_output.png)
        *Description: A snippet of the DataFrame illustrating the 'Final Topic' column and its values, demonstrating categorization.*
    * **Model Name Cleaning:** Standardizing and shortening iPhone model names (e.g., "iPhone 12 Pro Max" to "12 Pro Max") for better readability and consistent categorization in visualizations.
        ![Model Name Cleaning Code/Output](images/notebook_model_cleaning_output.png)
        *Description: Screenshot of the Python code snippet for the `REPLACE()` function or a similar cleaning logic, along with its output showing cleaner model names.*

### 3. Exploratory Data Analysis (EDA) (`final.ipynb`)

Initial analysis was performed to understand the data's characteristics and identify preliminary trends.

* **Distribution of Star Ratings:** Analyzing the overall distribution of positive, neutral, and negative ratings.
    ![Star Rating Distribution Plot](images/notebook_eda_star_rating.png)
    *Description: A histogram or bar chart showing the frequency of 1-star, 2-star, ..., 5-star ratings across the dataset.*
* **Complaint Volume Over Time:** Visualizing how the number of complaints has changed across months/years to identify any temporal patterns.
    ![Complaint Volume Over Time Plot](images/notebook_eda_complaint_volume_time.png)
    *Description: A line or area chart illustrating the trend of complaints from 2021 to 2025.*
* **Top Complaint Categories:** Identifying the most frequent complaint topics across all models.
    ![Top Complaint Categories Plot/Table](images/notebook_eda_top_complaints.png)
    *Description: A bar chart or table summarizing the count or percentage of each 'Final Topic'.*

### 4. Interactive Dashboard Development (`dashboard.twbx`)

The processed and analyzed data was then leveraged to create an interactive Tableau dashboard, facilitating stakeholder exploration and decision-making.

* **Data Connection:** The cleaned `dashboard_ready_data.csv` was connected to Tableau.
* **Visualization Design:** Charts were designed to address key business questions:
    * Distribution of Star Ratings per Model
    * Overall Complaint Distribution
    * Complaint Volume Over Time
    * Breakdown of Complaint Types for Each Model (using a highlight table for detailed comparison)
* **Interactivity:** Dashboard actions were implemented to allow users to filter the entire dashboard by selecting a specific iPhone model.

## 📂 Repository Contents
enewed-iphones-complaint-analysis/
├── data/
│   └── processed/
│       └── dashboard_ready_data.csv  # Cleaned dataset used for the dashboard
├── notebooks/
│   ├── clean_code.ipynb              # Notebook for initial data cleaning and preprocessing
│   └── final.ipynb                   # Notebook for further processing, EDA, sentiment, and topic modeling
├── dashboards/
│   └── iphone_complaint_dashboard.twbx # The Tableau Packaged Workbook
├── images/                           # Folder to store all screenshots for the README
│   ├── dashboard_overview.png
│   ├── dashboard_iphone_12_pro_max_filter.png
│   ├── dashboard_iphone_13_filter.png
│   ├── dashboard_iphone_14_pro_filter.png
│   ├── notebook_sentiment_analysis_output.png
│   ├── notebook_topic_extraction_output.png
│   ├── notebook_model_cleaning_output.png
│   ├── notebook_eda_star_rating.png
│   ├── notebook_eda_complaint_volume_time.png
│   └── notebook_eda_top_complaints.png
└── README.md                         # This README file
## 🚀 How to Run & View

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/saiyam-jain0/renewed-iphones-complaint-analysis.git](https://github.com/saiyam-jain0/renewed-iphones-complaint-analysis.git)
    cd renewed-iphones-complaint-analysis
    ```
2.  **Explore the Code (Optional):**
    * You can view the Jupyter Notebooks (`.ipynb` files) directly on GitHub by navigating to the `notebooks/` folder and clicking on `clean_code.ipynb` and `final.ipynb`. Note that some large or interactive outputs might not render directly on GitHub, hence the screenshots in this README.
3.  **View the Dashboard:**
    * Download the `dashboards/iphone_complaint_dashboard.twbx` file.
    * Open it using Tableau Public Desktop Edition (free download available from Tableau's website) or Tableau Desktop.

## 📚 Technologies Used

* **Python:** For data cleaning, preprocessing, sentiment analysis, and topic modeling.
    * `pandas`
    * `numpy`
    * `nltk` (for text processing)
    * `scikit-learn` (for potentially TF-IDF, clustering)
    * `matplotlib`
    * `seaborn`
* **Jupyter Notebook:** For interactive development and analysis.
* **Tableau Public Desktop Edition:** For interactive dashboard creation and visualization.

---

## 🙋‍♂️ About Me

* **Saiyam Jain**
* **Connect with me:** [LinkedIn](https://www.linkedin.com/in/saiyam-jain-368a23294/) | [GitHub](https://github.com/saiyam-jain0)

---
