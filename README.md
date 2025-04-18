# 🌸 Perfume Filter Engine

This project implements a **filter-based perfume selection tool** that allows users to search for perfumes matching specific criteria such as gender, season, sillage strength, and main accords. It is a simple yet powerful Python script designed for quick lookups from a perfume dataset.

## 📌 Project Summary

Instead of using machine learning or NLP, this script uses exact keyword matching across specific columns in a perfume database to return perfumes that satisfy all user-defined criteria.

## 📁 Dataset

- `perfume_data_combined.csv`  
  The dataset should contain at least the following columns:
  - `name`
  - `main accords `
  - `for_gender`
  - `seasons`
  - `sillage`

## ⚙️ How It Works

1. **Data Preparation**
   - The script reads the perfume data and splits the `for_gender` and `seasons` fields into lists.
   - It handles missing values to avoid errors during filtering.

2. **Search Function**
   - The `find()` function performs substring matching for each search term in a given column.
   - A perfume passes the filter only if **all specified search terms** are found in the column.

3. **Filtering**
   - Perfumes are filtered based on four user-defined criteria:
     - Gender (e.g., `"for women"`)
     - Season (e.g., `"winter"`)
     - Sillage (e.g., `"strong"`)
     - Main Accords (e.g., `"woody"`)

4. **Output**
   - The filtered results are printed directly to the console, showing the names of the perfumes that match **all** criteria.

## 🔍 Example Usage

```python
search_gender = ["for women"]
search_seasons = ["winter"]
search_sillage = ["strong"]
search_main = ["woody", "", ""]  # Empty strings are ignored

# Filtering...
result = list(set(main_accords_list) & set(gender_list) & set(sillage_list) & set(seasons_list))

for index in result:
    print(perfumedb["name"].iloc[index])
✅ Requirements
Python 3.x

pandas

Install dependencies:

bash
Copy
Edit
pip install pandas
🚀 How to Run
Place your dataset perfume_data_combined.csv in the same directory as the script.

Modify the search_gender, search_seasons, search_sillage, and search_main variables to match your desired filters.

Run the script to view the filtered perfume names.

🧠 Notes
String matching is case-sensitive. Make sure your search terms exactly match the dataset values.

This tool is ideal for building curated perfume selections or creating user-specific recommendations based on simple rules.

📎 Source Notebook
Originally developed in Google Colab.

