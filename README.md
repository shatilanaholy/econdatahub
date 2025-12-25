# EconDataHub: Public Use Data Sources for Economics

## Overview
**EconDataHub** is a specialized metadata repository and interactive web application designed to streamline data discovery for empirical economic research. Unlike general-purpose search engines, this platform provides a curated, constrained search environment tailored to the technical requirements of professional economists and students. It currently catalogs over 145 distinct data sources, including canonical longitudinal panels, national censuses, and administrative records from international organizations.

The project utilizes a modular architecture where the application logic (`index.html`) is separate from the data registry (`data.json`), ensuring the repository is scalable and easily maintainable.

## Key Features
* **Curated Data Registry:** A comprehensive list of 145+ unique sources across microeconomics, macroeconomics, finance, and international development.
* **Granular Filtering (7 Dimensions):** Navigate the repository using filters for Region, Country, Difficulty Level, Course Relevance, Data Structure, and Frequency.
* **Polysemic Search Logic:** Built-in support for multi-tagging ensures datasets correctly surface under multiple curriculum categories (e.g., the CPS appears under both "Labor" and "Public Economics").
* **Difficulty Level Classification:** Each source is categorized as Beginner (foundational), Intermediate (standard surveys), or Advanced (administrative or high-dimensional data) to signal technical requirements.
* **System-Aware Interface:** The application automatically adopts the viewer's OS or browser theme (Light/Dark mode) with a manual override toggle.
* **Immediate Metadata Insights:** Entries surface key variables, units of analysis, and canonical academic citations before the user leaves the site.

## Contribution
EconDataHub provides a distinct advantage over standard search engines by reducing the **transaction and search costs** (Stigler, 1961) associated with academic research:

1. **Econometric Alignment:** While Google indexes the entire web, it cannot filter by data structure. EconDataHub allows researchers to identify "Panel" or "Time Series" data instantly, ensuring a source fits an identification strategy before documentation review begins.
2. **Pedagogical Scaffolding:** By assigning difficulty tiers, the tool acts as a quality signal. It assists instructors in identifying datasets suitable for undergraduate term papers while guiding graduate students toward records that meet rigorous dissertation standards.
3. **Noise Mitigation:** Broad search engines often return irrelevant commercial reports or news articles. EconDataHub provides a filtered environment containing only high-quality, peer-reviewed, or official institutional data.
4. **Curriculum Mapping:** The project maps global datasets directly to the standard economics major curriculum, making it a direct pedagogical tool for students looking for data relevant to their specific coursework at the University of Nebraska-Lincoln.

## Technical Details for Adding Data Sources
To expand the registry, update the `data.json` file. Each new entry must follow this schema:

```json
{
  "name": "Name of the Dataset",
  "desc": "A brief description of content.",
  "region": "Geographic region (e.g., North America)",
  "country": "Specific country or 'Global'",
  "language": "English, Spanish, etc.",
  "unit": "Unit of analysis (e.g., Individual, Household)",
  "structure": "Cross-Sectional, Panel, or Time Series",
  "frequency": "Monthly, Quarterly, Annual, etc.",
  "curriculum": ["Labor", "Public"], 
  "tier": "Beginner",
  "url": "[https://link-to-data.org](https://link-to-data.org)",
  "vars": "Key variables (e.g., GDP, Wages)",
  "papers": "Canonical citation info."
}
```

## Critical Rules for Integration
* **Curriculum Array:** The curriculum field must be an array (enclosed in `[]`). This allows the "polysemic" filtering to work. For example, use ["Labor", "Macroeconomics"] if the data applies to both.
* **Tier Values:** The tier field should strictly use one of these three values: Beginner, Intermediate, or Advanced.
* **Course Names:** For the curriculum filter to find the data, use the standard names already in the dropdown: Labor, Energy, Trade, IO, Environmental, Game Theory, Public, Development, Finance, Econometrics, Macroeconomics, or Microeconomics.
* **Automated Sorting:** You do not need to worry about where you place the new item in the file. The JavaScript in index.html is programmed to sort the entire list alphabetically by name every time the page loads.

## Verification
After saving the updated `data.json`, simply refresh your browser. The "Showing X sources" counter will automatically increment, and your new entry will appear in the grid/table and be searchable via the filters.

## Author

**Shatil Anaholy**  
*Assistant Professor of Practice in Economics  
University of Nebraska - Lincoln*

## Disclaimer

The links and metadata provided in this resource were compiled for educational and research purposes. While efforts have been made to ensure accuracy, the URLs have not been individually verified at the time of publication and may be subject to change by the data providers. Please use these resources at your own discretion.
