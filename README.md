# 🗺 Google Maps Business Scraper

A flexible and extensible scraper built to extract structured business data from Google Maps based on user-defined search queries.

This tool enables automated collection of business information such as software companies, restaurants, agencies, or any category within a specific location — with optional review and website analysis.

---

# ✨ Key Capabilities

### 🔎 Dynamic Search Queries

Run custom searches like:

* *“software houses in New York”*
* *“restaurants in Chicago”*
* *“digital marketing agencies in London”*

The scraper adapts to any business + location combination.

---

### 📦 Structured Data Extraction

For each business, the scraper can collect:

* Business Name
* Website URL
* Phone Number
* Address
* Customer Reviews *(optional)*
* Social Media Links *(optional, extracted from business website)*

---

### 🧩 Optional Advanced Scraping

* **Review Scraping** → Collects user reviews from Google Maps
* **Website Scraping** → Visits the business website to extract social media profiles

Both features are configurable and disabled by default.

---

### 💾 Export Options

Output can be generated in:

* `CSV` format (ideal for spreadsheets & analytics)
* `JSON` format (ideal for APIs & structured processing)

---

# 🏗 Project Structure

The repository follows a modular architecture for maintainability and scalability.

```
├── Main.py                 # Application entry point
├── utils/
│   ├── Scraper.py          # Core Google Maps scraping logic
│   ├── DataHandler.py      # Output handling (CSV / JSON)
│   ├── Website_Scraper.py  # Extracts social links from business websites
│   ├── Pprints.py          # Clean terminal progress display
```

Each component is isolated for easier updates and feature extensions.

---

# ⚙ Installation

### 1️⃣ Clone the repository

```bash
git clone https://github.com/<your-username>/google-maps-scraper.git
cd google-maps-scraper
```

### 2️⃣ Install dependencies

```bash
pip install -r requirements.txt
```

---

# 🚀 How to Use

### Step 1: Configure Settings

Open `Main.py` and modify the configuration:

* **Search Query** → Business type + location
* **Output Format** → `"CSV"` or `"JSON"`
* **Review Scraping** → `True` / `False`
* **Website Scraping** → `True` / `False`

---

### Step 2: Run the Script

```bash
python Main.py
```

The scraper will begin extracting results and save the output in your chosen format.

---

# 🧪 Example Configuration

```python
from utils.Scraper import Scraper
from utils.DataHandler import DataHandler
from utils.Website_Scraper import WebsiteScraper

# Custom Configuration
search_query = "software houses in New York"
output_format = "CSV"        # Options: "CSV", "JSON"
review_scrape = True         # Enable review scraping
website_scrape = False       # Enable website scraping

if __name__ == "__main__":
    app = Main(
        headless_mode='--headless',
        reviews_scrape=True,
        output_format='csv',
        website_scrape=True
    )
    app.run()
```

---

# 📊 Output Format

### CSV Example

```
Name, Website, Phone, Address, Reviews, Social Media Links
```

---

### JSON Example

```json
[
  {
    "name": "Example Business",
    "website": "https://example.com",
    "phone": "+1-234-567-890",
    "address": "123 Example Street, New York, NY",
    "reviews": ["Review 1", "Review 2"],
    "social_media_links": ["https://twitter.com/example"]
  }
]
```

Fields related to reviews and social media will only appear if enabled.

---

# 🛠 Dependencies

* Python 3.8+
* Core libraries:

  * `requests`
  * `beautifulsoup4`
  * `pandas`
  * `json`
  * Additional dependencies listed in `requirements.txt`

---

# 🧱 Design Highlights

* Clean modular structure
* Config-driven behavior
* Easy format switching
* Optional deep scraping (reviews + website analysis)
* Suitable for lead generation, market research, and data analysis

---

# 🤝 Contributing

Contributions, improvements, and feature suggestions are welcome.
Feel free to open an issue or submit a pull request.

---

# 📄 License

Licensed under the MIT License. See the `LICENSE` file for full details.
