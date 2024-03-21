# Hybrid Skincare Recommendation System

Understanding that skincare efficacy is highly individualized. The impact of a product varies significantly across different skin types, with ingredients playing a crucial role in both the potential benefits and risks, such as irritation or allergic reactions. Additionally, this system acknowledges the consumer's interest in finding cost-effective products without compromising on quality. By exploring alternatives and ingredient substitutes that are more readily available, it is often possible to achieve similar results to those of higher-priced items.

The Skincare Product Recommendation System introduces a personalized method for suggesting skincare products, capitalizing on user reviews and detailed product data. Its goal is to align users with the skincare items that most closely align with their individual needs and preferences. This system seeks to simplify the often overwhelming process of choosing from the myriad skincare options on the market, thereby improving the shopping experience with customized recommendations. 


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
