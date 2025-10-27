[![Python](https://img.shields.io/pypi/pyversions/plotly)](./requirements.txt)
[![License](https://img.shields.io/badge/license-MIT-green)](./LICENSE)
[![DOI](https://zenodo.org/badge/387397007.svg)](https://zenodo.org/badge/latestdoi/387397007)

---

# Dutch Election Ads Analysis 🇳🇱

A longitudinal data analysis of political advertising practices in the Netherlands, using Meta’s **Facebook Ads Library API**.  
This project investigates how Dutch political parties have used targeted advertisements during the **2021, 2023, and 2025 general elections**, highlighting trends in reach, spending, and timing.

📊 [View the interactive analysis notebook](https://nbviewer.jupyter.org/github/pedrohserrano/facebook-ads-library-netherlands/blob/master/Facebook_Ads_API.ipynb)

<img src="assets/ads.png" alt="drawing" width="900"/>

---

## 🧩 Background

This project began as an adaptation of [Max Woolf’s](https://minimaxir.com) original **Facebook Ad Library Scraper**, which was initially developed for U.S. election data.  
Over time, it evolved into a dedicated analytical framework for **Dutch elections**, expanding to new electoral years and datasets.

The Dutch general elections took place:
- **2021** → March 15–17 (special COVID-19 voting measures)
- **2023** → November 22 transitionary period
- **2025** → After the cabinet fell under D. Schoof

---

## ⚙️ Software Overview

This repository includes an out-of-the-box **Python scraper** and accompanying analysis notebook for working with the official [Facebook Ad Library API](https://www.facebook.com/ads/library/api/).

**Core components:**
- `fb_ad_lib_scraper.py`: Downloads and cleans ad data via the Graph API.  
- `Facebook_Ads_API.ipynb`: Performs exploratory analysis and visualisation of campaign data.  
- `config.yaml`: API configuration parameters.  
- `TOKEN.txt`: Personal access token for Meta API.  
- `data/`: Contains cached datasets (running the analysis will overwrite existing files).

### Key Features
- Retrieves and cleans ads related to *“Social Issues, Elections or Politics”* (`Maatschappelijke kwesties, verkiezingen of politiek`)
- Automatically flattens nested JSON structures into clean data tables
- Handles missing demographic and regional data gracefully
- Produces CSVs ready for BI tools or Jupyter visualisation
- Designed for **research and transparency analysis**, not for commercial use

---

## 🚀 Usage

To use the API, you must first obtain access approval from Meta:

1. Register as a developer at [developers.facebook.com](https://developers.facebook.com/).  
2. Create a new app and generate an access token via the [Graph API Explorer](https://developers.facebook.com/tools/explorer).  
3. Save the token in `TOKEN.txt`.  
4. Adjust configuration parameters in `config.yaml`.  
5. Install dependencies and run the scraper.
```sh
pip3 install requests tqdm plotly
python3 fb_ad_lib_scraper.py
```

Outputs include:

| File | Description |
|------|--------------|
| `fb_ads.csv` | Raw ads and metadata |
| `fb_ads_demos.csv` | Demographic distributions (linked via `ad_id`) |
| `fb_ads_regions.csv` | Regional distributions (linked via `ad_id`) |

---

## 📈 Data Analysis

In the 2021 dataset, over **8,000 inactive ads** were collected using the query *"stem"* (“to vote” in Dutch).  
Highlights from the pilot study:
- **CDA** created the most unique ads (~2,000)
- **Volt** and **DENK** followed with 409 and 329 respectively
- **Forum voor Democratie (FVD)** had the highest total spending (~€220,000)
- Peak ad publishing occurred on **March 12**, the Friday before election day

📓 [Explore the full analysis notebook here](https://nbviewer.jupyter.org/github/pedrohserrano/facebook-ads-library-netherlands/blob/master/Facebook_Ads_API.ipynb)

<img src="assets/ads_province.png" alt="drawing1" width="800"/>


---

## 🙏 Attribution

This project is a derivative of [Max Woolf’s Facebook Ad Library Scraper](https://github.com/minimaxir/facebook-ad-library-scraper),  
initially designed for U.S. election data.  
All core scraping logic and structure were adapted and extended for the Dutch context.  

> Max’s open-source work is supported through [Patreon](https://www.patreon.com/minimaxir) and [GitHub Sponsors](https://github.com/sponsors/minimaxir).  
> If you found this project useful, please consider supporting his original repository.

---

## 📜 License and Citation

**Copyright (C) 2021–2025, Pedro V. Hernández Serrano**

Licensed under the [MIT License](./LICENSE).  
If you use or adapt this project in academic work, please cite the DOI badge above or the Zenodo record.

---
