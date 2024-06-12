# Hybrid Skincare Recommendation System

## Project Summary

### Introduction
This project introduces a personalized method for suggesting skincare products, leveraging user reviews and detailed product data. Its goal is to align users with products that match their individual needs and preferences, simplifying the overwhelming process of choosing skincare items and improving the shopping experience with customized recommendations.

### Dataset
- **Source**: web-scraped from Sephora
- **Tables**: Multiple review tables and a 'product_info.csv' table with 8494 entries and 27 features.
- **Focus**: Skincare products categorized into Moisturizers, Treatments & Serums, Cleansers, Eye Care, Masks, and Sunscreen.

### Exploratory Data Analysis
- **Primary and Secondary Categories**: Skincare is the most populated primary category. Subcategories refined to improve system relevance.
- **Review Distribution**: Most authors contributed a single review, with a small number of prolific reviewers.
- **Skin Type Reviews**: Over 60% of reviews come from individuals with combination skin.
- **Rating Distributions**: Common values around 4-5 stars, with long tails indicating outliers.
- **Correlation Heatmap**: High positive and negative correlations between specific variables, aiding in feature selection and preprocessing.

### Challenges
- **Imbalanced Data**: Predominance of reviews from combination skin users and one-time reviewers made it challenging to train models effectively.
- **Feature Selection**: Extensive visual analysis and dimensionality reduction techniques like PCA were necessary to choose relevant features from the dataset.

### Data Preprocessing
- **Cleaning**: Essential columns selected, ingredients cleaned and standardized.
- **Vectorization**: Ingredients transformed using TF-IDF.
- **Encoding**: Label Encoding for categorical attributes like 'skin_type' and 'secondary_category'.
- **Normalization**: Numerical features normalized to a common scale.
- **Interaction Weight**: Calculated to balance product relevance and user preference, enhancing recommendation accuracy.

### Model Selection
- **Objective**: Balance recall and precision to minimize false positives and maximize recommendation accuracy.
- **Models Evaluated**: LightFM, k-Nearest Neighbors (k-NN), and Singular Value Decomposition (SVD).
  - **LightFM**: AUC 0.820
  - **k-NN**: RMSE 0.282
  - **SVD**: RMSE 0.256

### Precision-Recall Analysis
- **LightFM**: Chosen for its robust performance, high AUC score, and ability to integrate both collaborative filtering and content-based methods, ensuring personalized recommendations.

### Final Model Choice
The LightFM model was selected for its strong capacity to deliver tailored recommendations, evidenced by its superior AUC score and balanced precision-recall metrics.

### Further Work
1. **Comprehensive Attribute Integration**: Incorporate attributes like submission time and review helpfulness for deeper insights.
2. **Ensemble Approach**: Combine strengths of SVD and k-NN models to enhance recommendation accuracy.
3. **Broader Feature Integration**: Include textual review analysis and product attributes for improved personalization.
4. **User Interface Development**: Create an intuitive interface to foster user engagement and gather feedback.
5. **Diversity and Novelty**: Prioritize diverse and novel recommendations to uncover less popular but relevant products.

This project aims to refine and expand the capabilities of the recommendation system, ensuring it remains at the forefront of personalization and user satisfaction in the skincare retail industry.

## Getting Started

These instructions will guide you in getting a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

Ensure you have the following prerequisites installed and set up:

- **Python Version**: Python 3.10.12 (recommended: 3.8 or higher)
- **Libraries and Dependencies**: Ensure all necessary libraries and dependencies are installed as listed in `requirements.txt`.
- **Google Account**: Required for Google Colab.
- **Local or Cloud Environment**: Capable of running Jupyter notebooks if not using Google Colab.

### Installation

Follow these steps to set up the project environment:

1. **Clone the repository**:
    ```bash
    git clone <repository-url>
    cd <repository-name>
    ```
2. **Install required Python packages**:
    ```bash
    pip install -r requirements.txt
    ```

### Running the Notebook

#### Google Colab

If you are using Google Colab, follow these instructions:

1. Open [Google Colab](https://colab.research.google.com/).
2. Click on `File` > `Open notebook` > `GitHub tab` and paste the URL of your notebook.
3. Alternatively, click on `File` > `Upload notebook` to upload the notebook file from your local machine.
4. Follow the instructions within the notebook to mount your Google Drive if required for data access or file storage.

#### Local Jupyter Installation

If you are running the notebook locally:

1. Launch Jupyter Notebook in your environment:
    ```bash
    jupyter notebook
    ```
2. Navigate to the notebook file in the Jupyter interface that opens in your web browser and open it.
3. Run the cells in the notebook sequentially to replicate the analysis.

### Setting Up the Kaggle API and Downloading the Dataset

To utilize datasets from Kaggle for your project, you'll need to configure the Kaggle API on your system. Follow these steps:

1. **Create or Log Into Your Kaggle Account**:
    - New users can [create an account](https://www.kaggle.com/).
    - Existing users can [log in](https://www.kaggle.com/account/login).

2. **API Token Generation**:
    - Navigate to your account settings by clicking on your profile picture in the top right corner and selecting 'Account'.
    - Scroll to the 'API' section and click the 'Create New API Token' button. This downloads a file named `kaggle.json`, containing your API credentials.

3. **Setup API Token on Your System**:
    - Place the downloaded `kaggle.json` file into the directory specified in your notebook. The standard location is `~/.kaggle/` for Unix-like systems.

4. **Explore the Dataset**:
    - Visit the [Sephora Products and Skincare Reviews](https://www.kaggle.com/datasets/nadyinky/sephora-products-and-skincare-reviews/data) page to explore and understand the dataset you'll be working with.

5. **Dataset Download and Setup**:
    - Execute the following commands in your notebook to set up the Kaggle API and download the dataset:

    ```bash
    # Create the necessary Kaggle directory
    !mkdir ~/.kaggle

    # Copy the kaggle.json file into your directory
    !cp /your/drive/kaggle.json ~/.kaggle/

    # Secure the API token by updating its permissions
    !chmod 600 ~/.kaggle/kaggle.json

    # Download the dataset from the Kaggle
    !kaggle datasets download -d nadyinky/sephora-products-and-skincare-reviews

    # Unzip the downloaded dataset into the specified directory
    !unzip /content/sephora-products-and-skincare-reviews.zip
    ```

By following these steps, you'll be able to securely set up the Kaggle API on your system and access the datasets required for your project.

## Authors

Valentina Sanchez <br />
[vsanchezn.cs@gmail.com](mailto:vsanchezn.cs@gmail.com)

## Acknowledgments

Inspiration, datasets, and code snippets for this project were provided by:

- [Sephora Products and Skincare Reviews by Nady Inky](https://www.kaggle.com/datasets/nadyinky/sephora-products-and-skincare-reviews/data) - Source of the Kaggle dataset.
