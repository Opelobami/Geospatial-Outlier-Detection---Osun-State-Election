# 🗳️ Osun State Election Geospatial Analysis

## 📍 Overview
This project investigates **voting irregularities in Osun State, Nigeria**, following widespread allegations of manipulation and inconsistencies in election results. The analysis applies **geospatial techniques** to identify polling units with voting patterns that deviate significantly from their neighbouring units which is a potential signs of influence or rigging.

---

## 🎯 Objectives
1. **Dataset Preparation**
   - Clean and enrich the Osun election dataset with geographic coordinates (Latitude and Longitude)
   - Ensure each polling unit has identifiable location data.

2. **Neighbour Identification**
   - Identify neighbouring polling units within a fixed radius (e.g., 1 km).
   - Use spatial proximity to define neighbourhoods for comparison.

3. **Outlier Detection**
   - Compute an **outlier score (Z-score)** for each polling unit and party.
   - Compare votes for each party against neighbouring units to detect abnormal deviations.

4. **Reporting & Visualization**
   - Highlight top outlier polling units.
   - Visualize results interactively on a geospatial map.
   - Produce a detailed analytical report.

---

## 🧰 Tools & Technologies
| Tool | Purpose |
|------|----------|
| **Python (Anaconda / Jupyter Notebook)** | Main analysis and computation |
| **GeoPandas** | Handling and analyzing spatial data |
| **Folium** | Interactive map visualization |
| **Pandas & NumPy** | Data cleaning and statistical operations |
| **Matplotlib / Seaborn** | Static visualizations |
| **Google Sheets + Geocode by Awesome Table** | Obtaining Latitude & Longitude |
| **Excel** | Sorting and reporting final outlier scores |

---

## 🔍 Analytical Workflow

### **1. Data Preparation**
- Cleaned and merged Ward, PU-Name, State, LGA, and "Nigeria" to generate Address column.    
- Generated Longtitude and Latitude from Address column using Geocode by Awesome Table on google Sheets.

---

### **2. Z-Score Computation**

Each polling unit’s score was standardized using the formula:

\[
Z = \frac{X - \mu}{\sigma}
\]

Where:
- **X** = polling unit vote count  
- **μ (mean)** = neighborhood average  
- **σ (SD)** = neighborhood standard deviation  

This helped identify **extreme deviations**, either unusually high (positive) or low (negative) values.

---

### **3. Neighborhood Statistics**

For each polling unit:
- **Neighbor Mean:** Average votes of nearby units within the same ward or cluster.  
- **Neighbor SD:** Standard deviation of those neighboring votes.

---

### **4. Outlier Detection**

Polling units with **high absolute Z-scores (>|2|)** were classified as **outliers**, signaling statistically significant deviations.

---

## 🗺️ Visualization

The core deliverable is an **interactive Folium map**:

This HTML map allows users to:
- Zoom and explore polling units.  
- View results per political party.  
- Identify high or low performing outlier areas.

**View Map:**  
👉 

---

## 📊 Key Findings (Summary)

### **APC**

| PU | Z-score | Neighbor Mean | Neighbor SD | Interpretation |
|----|----------|----------------|--------------|----------------|
| 1 | -79 | 138.5 | 0.5 | Extreme underperformance compared to nearby polling units. Possible data error or severe local shift. |
| 2 | 62.9 | 109.7 | 2.1 | Exceptionally strong APC turnout; likely a local stronghold. |
| 3 | 48.3 | 41.5 | 1.5 | Strong performance, well above neighborhood average. |

---

### **PDP**

| PU | Z-score | Neighbor Mean | Neighbor SD | Interpretation |
|----|----------|----------------|--------------|----------------|
| 1 | 53.5 | 2.0 | 2.0 | Extraordinary PDP support; extreme positive deviation. |
| 2 | -43.8 | 108.3 | 0.9 | Significant underperformance despite strong nearby results. |
| 3 | -37 | 153.5 | 1.5 | Weak turnout relative to neighborhood average. |

---

### **LP**

| PU | Z-score | Neighbor Mean | Neighbor SD | Interpretation |
|----|----------|----------------|--------------|----------------|
| 1 | 68 | 3.2 | 1.7 | Extremely high LP turnout; isolated surge. |
| 2 | 36.7 | 3.7 | 1.7 | Strong support cluster. |
| 3 | 35.9 | 2.5 | 3.4 | High deviation indicating unique local preference. |

---

### **NNPP**

| PU | Z-score | Neighbor Mean | Neighbor SD | Interpretation |
|----|----------|----------------|--------------|----------------|
| 1 | 254.4 | 0.2 | 0.4 | Extremely high anomaly; likely recording error or special-case scenario. |
| 2 | 143.1 | 0.08 | 0.34 | Massive deviation; strong NNPP influence in an isolated area. |
| 3 | 99.6 | 0.14 | 0.35 | Consistent outlier pattern in NNPP-dominant cluster. |

---

## 💡 Insights & Discussion

- Outlier detection highlights both **party strongholds** and **potential data irregularities**.  
- Some polling units recorded extreme deviations suggesting **unusual voter concentration** or **data entry inconsistencies**.  
- The combination of **Z-score analysis** with **neighborhood context** provides better understanding of **localized political behavior**.  

---

## 🏁 Conclusion

This project demonstrates how **spatial data science techniques** can uncover deeper insights in election datasets.  
By combining **geostatistical modeling** and **interactive mapping**, it reveals geographical voting behaviors, outliers, and possible anomalies across Osun State.

### **Future Extensions**
- Apply **Bayesian spatial modeling** for predictive mapping.  
- Integrate **demographic and socioeconomic data**.  
- Expand to analyze **multiple Nigerian states** for comparative insight.  

---

## 👨‍💻 Author

**Opeyemi Ayobami**  
_Data Analyst | Geospatial Enthusiast_  
📍 Nigeria  
📧 [Your email or LinkedIn here]  
🔗 GitHub: [@yourusername](https://github.com/yourusername)

---
