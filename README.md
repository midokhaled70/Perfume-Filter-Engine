
# 🌸 Perfume Filter Engine

A simple yet powerful Python-based filtering tool to help you find perfumes that match **specific user preferences** — including **gender**, **season**, **sillage**, and **main accords** — from a structured dataset.

---

## 📌 Overview

Rather than using complex machine learning models or NLP techniques, this tool relies on **exact keyword matching** to deliver precise perfume recommendations. It's ideal for quick filtering, rule-based selection, and building curated scent lists.

---

## 📂 Dataset Structure

Ensure your dataset file is named:

* `perfume_data_combined.csv`

And contains at least the following columns:

| Column Name    | Description                                 |
| -------------- | ------------------------------------------- |
| `name`         | Name of the perfume                         |
| `main accords` | Key scent descriptors (e.g., woody, floral) |
| `for_gender`   | Target gender (e.g., for women, unisex)     |
| `seasons`      | Preferred seasons (e.g., winter, summer)    |
| `sillage`      | Scent trail strength (e.g., strong, soft)   |

---

## ⚙️ How It Works

1. **Data Preparation**

   * Loads CSV data using `pandas`.
   * Converts multi-valued fields (like `for_gender` or `seasons`) into Python lists.
   * Cleans and handles missing data gracefully.

2. **Filtering Mechanism**

   * Uses a custom `find()` function to apply **substring matching** on each field.
   * Only returns perfumes that match **all selected criteria**.

3. **User-defined Search**

   * Specify your preferences in the following categories:

     * Gender
     * Seasons
     * Sillage strength
     * Main accords

4. **Console Output**

   * Matching perfume names are printed directly.

---

## 🚀 Quick Start

### ✅ Requirements

* Python 3.x
* `pandas` library

Install dependencies:

```bash
pip install pandas
```

### ▶️ Running the Script

1. Clone or download this repository.
2. Place `perfume_data_combined.csv` in the same directory as the script.
3. Open and modify the following variables in the script as needed:

```python
search_gender = ["for women"]
search_seasons = ["winter"]
search_sillage = ["strong"]
search_main = ["woody"]
```

4. Run the script:

```bash
python perfume_filter.py
```

5. View the matching perfume names in your console.

---

## 🔍 Example Code Snippet

```python
search_gender = ["for women"]
search_seasons = ["winter"]
search_sillage = ["strong"]
search_main = ["woody"]

# Perform filtering
result = list(
    set(main_accords_list)
    & set(gender_list)
    & set(sillage_list)
    & set(seasons_list)
)

# Display results
for index in result:
    print(perfumedb["name"].iloc[index])
```

---

## 🧠 Notes

* **String matching is case-sensitive** — make sure your filter values exactly match the dataset (e.g., `"for women"` not `"For Women"`).
* Empty strings in the search lists are automatically ignored.
* This tool works best for **rule-based filtering** and **curated selection building**.

---

## 📓 Origin

This project was initially developed in **Google Colab** and later adapted for local use.

---

## 💡 Future Improvements (Suggestions)

* Add case-insensitive search.
* Convert script into a CLI or web app (e.g., Streamlit or Flask).
* Add fuzzy matching (e.g., Levenshtein distance).
* Export filtered results to a CSV.
## **Autor**
**Mido Ahme **

