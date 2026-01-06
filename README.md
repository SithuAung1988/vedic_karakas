# karaka.json

**A structured, machine-readable database of Vedic Astrology significators (Karakas) of planets, zodiac signs, and houses.**

[![Status: In-Progress](https://img.shields.io/badge/Status-In--Progress-orange)](#roadmap-&amp;-current-status)
[![Data Format: JSON](https://img.shields.io/badge/Format-JSON-green)](https://www.json.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## 📌 Project Overview

This project provides a comprehensive JSON database of astrological significators (karakas) of planets, zodiac signs, and houses. 
The mission of this project is to bridge the gap between traditional Vedic Astrology research and modern software development. 
By transforming the massive, complex compilation into a structured database format, I aim to provide a resource that researchers, 
educators, and developers can easily integrate into their own applications and calculation engines.

## 🛠 Curation Process & Effort

Converting a work of this magnitude into a digital database requires significant attention to detail. 

While I utilized **Gemini AI** to assist with the data cleanup, **90% of the sanitization process was performed manually by me.**

## 🚀 Roadmap & Current Status

This database is being released in phases. Please see the current progress below:

- [x] **Planets (Grahas):** Fully integrated and ready for use.
- [ ] **Zodiac Signs (Rashis):** Planned for a future update.
- [ ] **Houses (Bhavas):** Planned for a future update.

## 📊 Data Schema (Planets)

The planetary significators are stored as arrays within the `planets` object. To maintain the Vedic Astrology tradition, 
the keys use the following 3-letter lowercase format:

* `sun`: Sun
* `mon`: Moon
* `mar`: Mars
* `mer`: Mercury
* `jup`: Jupiter
* `ven`: Venus
* `sat`: Saturn

The significators for 12 signs and 12 houses will be added in future releases.

## 💻 Usage (Python Example)

```python
import json

# Load the JSON
with open('karaka.json', 'r', encoding='utf-8') as f:
    db = json.load(f)

def get_karakas(data, planet):
    """
    Directly retrieves significators using traditional 3-letter codes.
    Example codes: 'sun', 'mon', 'mar', 'mer', 'jup', 'ven', 'sat'
    """
    return data['planets'].get(planet.lower(), [])

# Example Query using the traditional 'mon' for Moon
results = get_karakas(db, "mon")
if results:
    print(f"Total significators found: {len(results)}")
    print(f"First 5 results: {results[:5]}")
else:
    print(f"No data found.")
```

## 📜 Source & Attribution

The astrological data within this database was originally compiled by:

* **Author:** Mr. Kanak Bosmia (Editor, KP-Ezine)
* **Source:** [KP Navaratnamala - Series 1 (Published May 2009)](https://ia601303.us.archive.org/35/items/kp-readers/kp%20navratnamala%201-3.pdf)

**All credit for the primary research, compilation, and astrological expertise belongs to Mr. Bosmia.** 

My contribution is strictly the digital transformation and structural architecture of the data for the benefit of the vedic astrology community.

## ⚖️ License

This project is released under the **MIT License**. 

*Note: The license applies to the JSON structure and digital database format. The intellectual property/credit for the underlying compilation remains with the original author.*

## ⚠️ Disclaimer & Accuracy

Because the original compilation is massive and highly complex, I take no responsibility for the absolute correctness or error-free nature of this database. Despite my best efforts in manual sanitization, the scale of the material means errors may exist.

**Important:** If your application or research requires 100% precision, please refer to Mr. Bosmia’s original work.

## 🤝 Contributing

If you find a typo or an incorrect significator mapping compared to the original text, please open an **Issue** or submit a **Pull Request** to help improve this resource for others.

## 🙏 Special Thanks

I would like to extend my deepest gratitude to **Mr. Kanak Bosmia**. 
His profound dedication to the study of Vedic Astrology and exhaustive efforts in compiling these massive amount of data are the foundation of this project. 
Without his great effort, this digital resource would not be possible. Thank you for your invaluable contribution to the community.