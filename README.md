# Women Economic Autonomy 2018 - MEData Analysis

Data exploration and visualization of the "Autonomía Económica Secretaría de las Mujeres 2018" (Economic autonomy, Women's secretariat 2018) dataset from Medellín's open data platform.

## 📊 About the Dataset

This dataset contains information from 1,572 women who participated in the economic empowerment program in Medellín during 2018. It reflects the interests and needs of women accessing the economic pathway program.

- **Source**: [MEData - Medellín Open Data Platform](http://medata.gov.co/dataset/autonom%C3%ADa-econ%C3%B3mica-secretar%C3%ADa-de-las-mujeres-2018)
- **Author**: Secretaría de las Mujeres (Women's Secretariat)
- **Year**: 2018
- **Records**: 1,572 entries
- **Original Columns**: 111 features (97 after cleaning)

## 🚀 Technical Implementation

### Technologies Used

- **Python 3.x**
- **Pandas**: Data manipulation and analysis
- **Matplotlib**: Data visualization
- **Seaborn**: Statistical data visualization
- **Google Colab**: Cloud-based Jupyter notebook environment

### Project Structure

```
Women-economic-autonomy-2018-MEData/
│
├── Economic_Autonomy_Secretaría_de_las_Mujeres_2018.ipynb
├── README.md
└── autonomia_economica_secretaria_mujeres_2018.csv (external)
```

### Data Processing Pipeline

#### 1. **Data Import**
```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load CSV with semicolon delimiter
women_dataframe = pd.read_csv(path, delimiter=";", low_memory=False, parse_dates=True)
```

#### 2. **Data Cleaning**

- **Handling Missing Values**: NaN values replaced with "Sin información" (No information)
- **Column Reduction**: Dropped 14 irrelevant columns, reducing from 111 to 97 features
- **Data Standardization**: 
  - Normalized capitalization across all columns
  - Fixed misspellings (e.g., "Union libre" → "Unión libre")
  - Standardized categorical values (e.g., time ranges, yes/no responses)
  - Unified ethnic group classifications
  - Corrected encoding issues (e.g., "CC\xa0" → "CC")

#### 3. **Data Transformation**

- **Column Renaming**: Simplified column names for better readability
  - `'Estado Civil:'` → `'Estado Civil'`
  - `'Barrio o Vereda (Tomar del listado oficial SUB)'` → `'Barrio/Vereda'`
  - Lengthy questions shortened to improve analysis workflow

- **Value Replacement**: Applied systematic replacement across 80+ variations to ensure data consistency

### 📈 Analysis & Visualizations

The notebook includes several key visualizations:

1. **Socioeconomic Distribution**
   - Count plot of participants by socioeconomic stratum
   - Shows value counts above each bar

2. **Ethnic Group Analysis**
   - Pie chart displaying percentage distribution
   - Includes categories: Mestiza, Indígena, Negra, Otro

3. **Mother Head of Household**
   - Bar chart showing approximately 50% are single mothers

4. **Entrepreneurship Challenges**
   - Analysis of gender-related difficulties in business development
   - Most respondents indicated gender wasn't a significant barrier

5. **Business Support**
   - Distribution of women receiving entrepreneurial support

6. **Marital Status**
   - Both count and pie chart visualizations
   - Categories: Soltera, Unión libre, Casada, Separada, Viuda, Divorciada

### 🎨 Visualization Techniques

- **Seaborn countplot**: For categorical frequency distributions
- **Matplotlib pie charts**: For percentage-based comparisons
- **Custom annotations**: Value labels displayed on all bar charts
- **Color palettes**: 'Set2' and 'husl' for aesthetic consistency

## 🔧 Setup & Usage

### Prerequisites

```bash
pip install pandas matplotlib seaborn
```

### Running the Analysis

1. **Google Colab** (Recommended):
   - Click the "Open in Colab" badge in the notebook
   - Mount your Google Drive
   - Place the CSV file in: `/content/drive/MyDrive/Economic Autonomy Dataset/`
   - Run all cells

2. **Local Environment**:
   - Clone this repository
   - Install dependencies
   - Update the file path in cell 5 to your local CSV location
   - Run the Jupyter notebook

```bash
git clone https://github.com/laurash96/Women-economic-autonomy-2018-MEData.git
cd Women-economic-autonomy-2018-MEData
jupyter notebook
```

## 📋 Data Dictionary

Key features analyzed include:
- **Demographics**: Age, marital status, ethnic group, neighborhood/district
- **Socioeconomic**: Stratum, housing situation
- **Family**: Head of household status, dependents
- **Business**: Stage of entrepreneurship, sector, challenges faced
- **Support**: Current programs, training needs, financing sources

## 🔍 Key Findings

- Majority of participants are from stratum 2
- Approximately 50% are single mothers (madre cabeza de hogar)
- Most common marital status: Soltera (Single)
- Gender was not reported as a primary barrier to entrepreneurship by most respondents
- Diverse representation across ethnic groups with Mestiza being the majority

## 📝 License

This project uses open data provided by the city of Medellín through the MEData platform.

## 👥 Author

Laura Saldarriaga Higuita
- GitHub: [@laurash96](https://github.com/laurash96)

## 🔗 Links

- [Dataset on MEData](http://medata.gov.co/dataset/autonom%C3%ADa-econ%C3%B3mica-secretar%C3%ADa-de-las-mujeres-2018)
- [Open in Google Colab](https://colab.research.google.com/github/laurash96/Women-economic-autonomy-2018-MEData/blob/main/Economic_Autonomy_Secretar%C3%ADa_de_las_Mujeres_2018.ipynb)
