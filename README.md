# EconDataHub: Public Use Data Resources for Economics

## Overview
**EconDataHub** is a single-page interactive web application designed to assist academic economists, researchers, and students in navigating the fragmented landscape of global public-use data. This tool serves as a centralized metadata repository, cataloging over 100 distinct data sources suitable for empirical research in fields such as applied microeconomics, macroeconomics, finance, and international development.

## Key Features

* **Comprehensive Registry:** Contains metadata for over 110 unique data sources, ranging from canonical US microdata (e.g., CPS, PSID, NLSY) to international macroeconomic indicators (e.g., World Bank WDI, Eurostat).
* **Advanced Filtering:** Users can filter the repository by:
    * **Region** (North America, Europe, Asia, Africa, Latin America, Oceania, Global)
    * **Country** (Dynamic list populated based on available sources)
    * **Economic Field** (Labor, Public Econ, Development, Finance, etc.)
    * **Data Structure** (Panel, Cross-Sectional, Time Series)
    * **Frequency** (Annual, Quarterly, Monthly, Daily)
* **Smart Search:** Real-time search functionality allows users to locate datasets by name, variable, or topic.
* **Adaptive Interface:** Features a responsive design with toggleable **Grid** and **Table** views.
* **Dark Mode:** Integrated dark mode support (AMOLED black) for comfortable viewing in low-light environments.
* **Detailed Insights:** Each entry includes specific details on key variables, language, frequency, and academic citations.

## Technical Details for Adding More Data Sources

The data file is separated from the index file. So, update the data.json file by following the schema -
{
  "name": "Name of the Dataset",
  "desc": "A brief description of what the data contains.",
  "region": "The broad geographic region (e.g., Asia, North America)",
  "country": "The specific country or 'Global'",
  "language": "English, Spanish, etc.",
  "unit": "The unit of analysis (e.g., Individual, Household, National)",
  "structure": "Cross-Sectional, Panel, or Time Series",
  "frequency": "Monthly, Quarterly, Annual, etc.",
  "curriculum": ["Labor", "Public"], 
  "tier": "Beginner",
  "url": "https://link-to-data.org",
  "vars": "Key variables like GDP, Wages, etc.",
  "papers": "Canonical citation or impact info."
}

# Critical Rules for Integration
* **Curriculum Array:** The curriculum field must be an array (enclosed in []). This allows the "polysemic" filtering to work. For example, use ["Labor", "Macroeconomics"] if the data applies to both.
* **Tier Values:** The tier field should strictly use one of these three values: Beginner, Intermediate, or Advanced.
* **Course Names:** For the curriculum filter to find the data, use the standard names already in the dropdown: Labor, Energy, Trade, IO, Environmental, Game Theory, Public, Development, Finance, Econometrics, Macroeconomics, or Microeconomics.
* **Automated Sorting:** You do not need to worry about where you place the new item in the file. The JavaScript in index.html is programmed to sort the entire list alphabetically by name every time the page loads.

# Verification
After saving the updated data.json, simply refresh your browser. The "Showing X sources" counter will automatically increment, and your new entry will appear in the grid/table and be searchable via the filters.

## Author

**Shatil Anaholy**
Assistant Professor of Practice in Economics
University of Nebraska - Lincoln

## Disclaimer

The links and metadata provided in this resource were compiled for educational and research purposes. While efforts have been made to ensure accuracy, the URLs have not been individually verified at the time of publication and may be subject to change by the data providers. Please use these resources at your own discretion.
