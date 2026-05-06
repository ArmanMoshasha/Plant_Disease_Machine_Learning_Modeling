# Plant Disease Machine Learning Modeling

The goal of this project is to investigate whether environmental, spatial, and ecological variables can help predict plant disease incidence. The main question being addressed is:

Can climate and ecological predictors such as temperature, precipitation, location, year, habitat type, and natural/agricultural system type explain variation in plant disease incidence?**

This project began with exploratory data analysis to understand the structure of the data, then expanded into machine learning modeling to compare how different models perform when predicting disease incidence.

## Project Overview

This repository contains end-to-end machine learning pipelines for identifying and classifying plant diseases. The project leverages the Dyrad dataset and uses state-of-the-art deep learning models to achieve high accuracy in disease detection.

## Techniques Used

This project uses several techniques

- Data cleaning and preprocessing
- Exploratory data analysis
- Data visualization
- Summary statistics
- Feature selection
- One-hot encoding of categorical variables
- Log transformation of a skewed response variable
- Train/test split validation
- Supervised machine learning models:
- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor
- Neural Network
- Unsupervised machine learning:
- K-means clustering
- Model evaluation using:
- Mean Squared Error
- R² score

## Features

- **Exploratory Data Analysis (EDA)** - Comprehensive data exploration and visualization
- **Deep Learning Models** - Pre-trained and custom neural networks for disease classification
- **Data Preprocessing** - Image normalization and augmentation techniques
- **Model Evaluation** - Performance metrics and visualization of results

## Project Structure

```
Plant_Disease_Machine_Learning_Modeling/
├── Dyrad Dataset project1/
│   ├── notebooks/
│   │   ├── 01_preliminary_eda.ipynb       # Initial data exploration
│   │   └── 02_modeling.ipynb               # Model training and evaluation
│   └── [datasets and outputs]
├── .gitattributes
└── README.md
```

## Getting Started

## Dataset Source

The project uses two related datasets:

1. **Plant disease dataset**  
   Contains plant disease observations, including disease incidence, infected counts, host information, habitat, location, year, and ecological system type.

2. **Climate dataset**  
   Contains climate variables matched to the disease observations, including:
   - `bio01`: temperature variable
   - `bio12`: precipitation variable

The datasets are stored in the project repository under:

```
Dyrad Dataset project1/data/raw/

### Prerequisites

- Python 3.8 or higher
- Jupyter Notebook or JupyterLab
- Virtual environment (recommended)

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/ArmanMoshasha/Plant_Disease_Machine_Learning_Modeling.git
   cd Plant_Disease_Machine_Learning_Modeling
   ```

2. **Create a virtual environment:**
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # On Windows: .venv\Scripts\activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
   (If requirements.txt is not present, install key packages manually)

4. **Launch Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```

## Notebooks

### 01_preliminary_eda.ipynb
- Dataset loading and exploration
- Data visualization and statistical analysis
- Data quality checks
- Class distribution analysis

### 02_modeling.ipynb
- Model architecture design
- Training and validation
- Hyperparameter tuning
- Performance evaluation
- Result visualization

## Datasets

This project uses the **Dyrad dataset** for plant disease classification. The dataset contains labeled images of plant leaves with various diseases. https://datadryad.org/dataset/doi:10.5061/dryad.p8cz8wb0h

## Technologies Used

- **Python** - Programming language
- **TensorFlow/Keras** - Deep learning framework
- **Pandas & NumPy** - Data manipulation
- **Matplotlib & Seaborn** - Data visualization
- **Scikit-learn** - Machine learning utilities
- **Jupyter** - Notebook environment

## Results

Model performance metrics and visualizations are documented within the notebooks. Results include:
- Classification accuracy
- Confusion matrices
- ROC-AUC curves
- Feature importance analysis

## Usage

1. Navigate to the `Dyrad Dataset project1` folder
2. Open the notebooks in Jupyter
3. Run cells sequentially to:
   - Explore and understand the data (01_preliminary_eda.ipynb)
   - Train and evaluate models (02_modeling.ipynb)

## Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues for bugs and feature requests.

## License

This project is open source

## Author

**Arman Moshasha**
- GitHub: [@ArmanMoshasha](https://github.com/ArmanMoshasha)

## Acknowledgments

- Dyrad team for providing the dataset
- Open-source machine learning community

## Contact

For questions or inquiries, please reach out via GitHub

---

The EDA showed that disease incidence was not spread out evenly across the dataset. Most of the values were close to zero, meaning many observations had little to no disease, while only a smaller number had high disease incidence. Because of that, I used a log1p transformation before modeling to make the data less skewed while still keeping the zero values. The early graphs also showed that temperature and precipitation alone did not clearly explain disease incidence.

After adding more features and testing different models, Linear Regression performed the weakest, which makes sense because the relationship does not seem to be simple or linear. The Decision Tree, Random Forest, and Neural Network models did better, with Random Forest performing the best overall. This suggests that plant disease incidence is probably affected by a mix of factors, including climate, location, year, habitat, and whether the system is natural or agricultural. The model still does not explain everything, so adding more biological details, like host species and pathogen type, would probably improve the project in the future.

