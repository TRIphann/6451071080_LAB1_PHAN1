# 6451071080 - LAB 1 - PART 1

Data Mining practical lab, Part 1: data preprocessing and exploratory data analysis with pandas, matplotlib and seaborn.

Student: Phan Cong Tri - 6451071080

## Contents

| Folder | Dataset | Notebooks |
| --- | --- | --- |
| `6451071080_LAB1_Bai2_Trang15-17` | `titanic.csv` | 6 notebooks |
| `6451071080_LAB1_Bai2_Trang28` | `bank-full.csv`, `bank.csv`, `bank-names.txt` | 6 notebooks |
| `6451071080_LAB1_Bai2_Trang30` | `tb_tracking.xlsx`, `tb_tracking.csv`, `tb_tracking_processed.csv` | 6 notebooks + 1 preprocessing notebook |

## Exercise 2 (pages 15-17) - Titanic dataset

| Question | Task |
| --- | --- |
| Cau 1 | Load `titanic.csv` and inspect the first 12 rows |
| Cau 2 | Count missing values and concatenate the train and test splits |
| Cau 3 | Compare age distributions of surviving and non-surviving female passengers with `histplot` |
| Cau 4 | Build a `FacetGrid` over `embarked` with a `pointplot` of survival by passenger class and sex |
| Cau 5 | Plot a `catplot` of survival rate by family size |
| Cau 6 | Feature engineering: extract the deck letter from the cabin column, fill missing `embarked` and `age`, drop unused columns |

## Exercise 3 (page 28) - Bank marketing dataset

| Question | Task |
| --- | --- |
| Cau 1 | Load `bank-full.csv` with typed columns and inspect the first 12 rows |
| Cau 2 | Count missing values and concatenate the data frames |
| Cau 3 | Compare age distributions of subscribers and non-subscribers for each housing loan group |
| Cau 4 | Build a `FacetGrid` over `contact` with a `pointplot` of subscription rate by education and marital status |
| Cau 5 | Plot a `catplot` of subscription rate against the number of campaign contacts |
| Cau 6 | Map `poutcome` to numeric codes and inspect the resulting distribution |

## Exercise 4 (page 30) - Environment tracking dataset

The raw workbook `tb_tracking.xlsx` is exported to `tb_tracking.csv` and cleaned in `6451071080_LAB1_Bai2_XuLyDuLieu.ipynb`:

- add the header row `id, device_id, co_level, humidity, temperature, time`
- drop measurements taken before 03/01/2018 because the sensor was recalibrated on that date
- split `time` into a measurement timestamp and a `minutes` column (minutes elapsed within the day)

The cleaned output is written to `tb_tracking_processed.csv`, which all six question notebooks read.

| Question | Task |
| --- | --- |
| Cau 1 | Load `tb_tracking_processed.csv` and inspect the first rows |
| Cau 2 | Count missing values and concatenate the data frames |
| Cau 3 | Compare temperature distributions of device 99005 against the other devices using a high/low threshold |
| Cau 4 | Build a `FacetGrid` over `device_id` with a `pointplot` of CO level by hour and temperature group |
| Cau 5 | Plot a `catplot` of CO level by time of day and temperature group |
| Cau 6 | Map `device_id` to deck identifiers and apply the same text-extraction logic as the sample code |

## Layout

```
6451071080_Lab1_PHAN1/
|-- README.md
|-- requirements.txt
|-- .gitignore
|-- 6451071080_LAB1_Bai2_Trang15-17/
|   |-- 6451071080_LAB1_Bai2_Cau1.ipynb ... Cau6.ipynb
|   `-- titanic.csv
|-- 6451071080_LAB1_Bai2_Trang28/
|   |-- 6451071080_LAB1_Bai2_Cau1.ipynb ... Cau6.ipynb
|   |-- bank-full.csv
|   |-- bank.csv
|   `-- bank-names.txt
`-- 6451071080_LAB1_Bai2_Trang30/
    |-- 6451071080_LAB1_Bai2_XuLyDuLieu.ipynb
    |-- 6451071080_LAB1_Bai2_Cau1.ipynb ... Cau6.ipynb
    |-- tb_tracking.xlsx
    |-- tb_tracking.csv
    `-- tb_tracking_processed.csv
```

## How to run

Every notebook reads its dataset by a relative path, so start Jupyter from the folder that contains the notebook.

```bash
pip install -r requirements.txt
jupyter notebook
```

Open the question notebook you want to run, for example `6451071080_LAB1_Bai2_Trang15-17/6451071080_LAB1_Bai2_Cau1.ipynb`, and run all cells.

## Dependencies

Python 3.14 with the packages listed in `requirements.txt`:

- pandas 3.1.0
- numpy 2.5.4
- matplotlib 3.11.2
- seaborn 0.13.2
- openpyxl 3.1.5 (required to read the `.xlsx` workbook)
