# 💻 Laptop Dataset Cleaning Project

This project focuses on cleaning and preprocessing a real-world laptop dataset using Python and Excel. The goal was to convert messy, inconsistent, and partially missing data into a clean and structured format suitable for further analysis or visualization.

---

## 📁 Dataset Source

- File name: `laptopData.csv`
- Contains information about laptops including brand, type, screen size, resolution, CPU specs, RAM, memory type, GPU, OS, weight, and price.
- Original file contained missing values, inconsistent units, and unstructured storage data.

---

## 🧼 Cleaning Steps Performed

### ✅ 1. **Importing Libraries**
Used:
- `pandas` for data manipulation
- `numpy` for handling missing values
- `matplotlib` for future visualizations

### ✅ 2. **Initial Cleanup with Python**
- Loaded CSV file using `pd.read_csv`
- Dropped the unnecessary `Unnamed: 0` column
- Renamed columns for better readability
- Replaced `"?"` with `NaN`
- Converted columns like `ram_gb`, `inches`, and `weight_kg` to proper numeric types
- Imputed missing values:
  - `inches` and `weight_kg` with column mean
  - `memory` at row 770 with `"256GB SSD"`
- Dropped any remaining rows with missing values
- Saved the cleaned version as `"cleaned dataset.csv"`

### ✅ 3. **Memory Column Decomposition in Excel**
Using Excel formulas and logic, the unstructured `memory` column was split into:

- `ssd_gb`: Total SSD capacity in GB
- `hdd_gb`: Total HDD capacity in GB
- `flash_storage_gb`: Flash-based storage capacity
- `hybrid_gb`: Capacity of hybrid storage (converted TB to GB where needed)
- `total_storage_gb`: Sum of all above storage types per laptop

This transformation handled:
- Combined entries like `"128GB SSD + 1TB HDD"`
- Variations like `"1.0TB Hybrid"` or `"32GB Flash Storage"`
- Converted TB to GB for standardization

---

## 🧪 Summary of Changes

| Column             | Change Type       | Description                                  |
|--------------------|-------------------|----------------------------------------------|
| `ram_gb`           | Converted to float | Removed "GB", now numeric                    |
| `weight_kg`        | Converted to float | Removed "kg", now numeric                    |
| `inches`           | Filled & rounded   | Missing values filled with mean              |
| `memory`           | Parsed & removed   | Split into detailed storage columns in Excel |
| `ssd_gb`           | New column         | Extracted from `memory`                      |
| `hdd_gb`           | New column         | Extracted from `memory`                      |
| `flash_storage_gb` | New column         | Extracted from `memory`                      |
| `hybrid_gb`        | New column         | Extracted from `memory`                      |
| `total_storage_gb` | New column         | Sum of all storage components                |
| `Unnamed: 0`       | Dropped            | Redundant index column                       |

---

## 📊 Possible Future Analysis

- Compare price vs total storage or RAM
- Filter ultrabooks with SSD-only configuration
- Brand-wise analysis of average specs
- Visualize GPU type distribution
- Build interactive dashboards in Power BI

---

## 🛠 Tools Used

- **Python** (pandas, numpy)
- **Excel** (formulas)
- **Jupyter Notebook** (for Python scripts)

---

## 🙋‍♀️ Author

**Niharika Pandey**  
[LinkedIn](https://www.linkedin.com/in/niharika-pandey-222256227)




