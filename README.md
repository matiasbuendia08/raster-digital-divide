# 🌙 Raster Digital Divide — Cusco Region, Peru

> **Course:** Python Programming — Applied Data Science  
> **Author:** Matias Buendia  
> **Dataset:** NASA Black Marble VNL 2025 × OSIPTEL Mobile Coverage 2019

---

## 📌 Research Question

How deep is the territorial digital divide in the Cusco region, Peru?  
This project cross-references NASA nighttime lights (urbanization proxy) with  
OSIPTEL mobile coverage density (internet access proxy) to expose inequality  
patterns between connected urban zones and digitally excluded rural areas.

---

## 📂 Input Data

Download the input raster files and place them inside your local `data/` folder  
before running the notebook. **Do not commit these files to your repository.**

| File | Description | Native CRS |
|------|-------------|------------|
| `VNL_cusco_2025.tif` | NASA Black Marble nighttime radiance (nW·cm⁻²·sr⁻¹) | EPSG:4326 |
| `kernel_cobmovil2019_50m.tif` | Mobile coverage kernel density (50m kernel) | EPSG:32719 |

> **Note:** If `kernel_cobmovil2019_50m.tif` fails to open, download  
> `Cobmovil_raster_opcional.zip` from the course Drive folder as an alternative.

---

## 🗂️ Repository Structure
raster-digital-divide/
│
├── data/                                  # Input rasters (not committed)
│   ├── VNL_cusco_2025.tif
│   └── kernel_cobmovil2019_50m.tif
│
├── notebooks/
│   └── digital_divide_cusco.ipynb        # Main analysis notebook
│
├── output/
│   ├── vnl_norm.tif                      # Normalized nighttime lights
│   ├── conn_norm.tif                     # Normalized connectivity
│   ├── ibd_brecha_digital.tif            # Digital Divide Index raster
│   ├── clasificacion_brecha.tif          # 4-category classification raster
│   └── dashboard_brecha_digital.png      # Final composite figure
│
├── README.md
└── requirements.txt

---

## ⚙️ Dependencies and Installation

```bash
pip install -r requirements.txt
```

Required libraries:

| Library | Purpose |
|---------|---------|
| `rasterio` | Raster I/O and reprojection |
| `numpy` | Array operations and normalization |
| `matplotlib` | Map visualization |
| `scipy` | Gaussian filter and statistical tests |
| `seaborn` | KDE distribution plots |
| `pandas` | Classification summary table |

---

## 🚀 How to Run

1. Clone the repository and install dependencies:
```bash
git clone https://github.com/matiasbuendia08/raster-digital-divide.git
cd raster-digital-divide
pip install -r requirements.txt
```

2. Place the input rasters inside `data/`

3. Open the notebook:
```bash
jupyter notebook notebooks/digital_divide_cusco.ipynb
```

4. Run all cells top to bottom: **Kernel → Restart & Run All**

---

## 🗺️ Output Files

| File | Description |
|------|-------------|
| `vnl_norm.tif` | Normalized nighttime lights raster [0–1] |
| `conn_norm.tif` | Normalized mobile connectivity raster [0–1] |
| `ibd_brecha_digital.tif` | Digital Divide Index raster [-1 to 1] |
| `clasificacion_brecha.tif` | 4-category territorial classification raster |
| `dashboard_brecha_digital.png` | Final composite 6-panel dashboard |

---

## 📊 Main Findings

96.97% of the Cusco territory falls into the **Critical Divide** category, with  
neither nighttime light nor mobile connectivity. Only 0.20% is classified as  
**Urban Connected**. A Welch t-test confirms a statistically significant difference  
between urban and rural zones (Cohen's d = 2.65, p ≈ 0), revealing a severe and  
persistent territorial digital divide across the Cusco region.

---

## 📄 License

MIT
