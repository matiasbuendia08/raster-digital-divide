# Raster Digital Divide — Cusco Region, Peru

## Research Question
How deep is the territorial digital divide in the Cusco region,
measured by crossing NASA nighttime lights (urbanization proxy)
with OSIPTEL mobile coverage density (connectivity proxy)?

## Dependencies and Installation
```bash
pip install -r requirements.txt
```

## How to Run
1. Place `VNL_cusco_2025.tif` and `kernel_cobmovil2019_50m.tif` inside `data/`
2. Open `notebooks/digital_divide_cusco.ipynb`
3. Run all cells top to bottom (Kernel → Restart & Run All)

## Output Files
| File | Description |
|------|-------------|
| `vnl_norm.tif` | Normalized nighttime lights raster [0–1] |
| `conn_norm.tif` | Normalized mobile connectivity raster [0–1] |
| `ibd_brecha_digital.tif` | Digital Divide Index raster [-1 to 1] |
| `clasificacion_brecha.tif` | 4-category territorial classification raster |
| `dashboard_brecha_digital.png` | Final composite dashboard figure |

## Main Findings
96.97% of the Cusco territory falls into the "Critical Divide" category,
with neither nighttime light nor mobile connectivity. Only 0.20% is classified
as "Urban Connected". A Welch t-test confirms a statistically significant
difference between urban and rural zones (Cohen's d = 2.65, p ≈ 0),
revealing a severe and persistent territorial digital divide.
