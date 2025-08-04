# Paraguayan Export Networks: Soybean and Beef Sectors

This repository contains the construction and analysis of co-export networks for two key commodity sectors in Paraguay: **soybeans** and **beef**. The goal is to explore structural patterns of exporter relationships, identify central firms, and detect communities of firms based on shared destination markets over time.

The analysis is based on data from the **Trase Initiative**, with a focus on firm-level exports, volumes, land use, and destination countries.

## Repository Structure

```
├── edges_nodes_soy.ipynb         # Soybean: edge and node construction
├── network_soy.ipynb             # Soybean: full network analysis
├── edges_nodes_beef.ipynb        # Beef: edge and node construction
├── network_beef.ipynb            # Beef: full network analysis
├── data/                         # Raw input files
│   ├── paraguay_soy_v1_2_6.csv
│   └── paraguay_beef_v1_2_4.csv
├── output/                       # Generated edge/node lists and Gephi exports
│   ├── soybean_coexport_edges.csv
│   ├── soybean_export_nodes.csv
│   ├── nodes_gephi_soja.csv
│   ├── beef_coexport_edges.csv
│   ├── beef_export_nodes.csv
│   └── nodes_gephi_carne.csv
```

## Methodological Overview

Each network represents **co-export relationships** between firms that shipped to the same country in the same year. The process involves:

- **Edge construction**: Pairs of exporters linked by shared destination-year co-occurrence; edge weight = combined FOB value.
- **Node construction**: Exporters aggregated by total FOB value, volume, and land use.
- **Centrality analysis**: Degree, betweenness, closeness, eigenvector centralities.
- **Community detection**: Louvain modularity-based algorithm.
- **Structural indicators**: Network density, average degree, modularity.
- **PageRank and transnational firm flag**.

All analysis is performed using `NetworkX`, `pandas`, `matplotlib`, and `community-louvain`.

## Data Source

- **Trase SEI-PCS Paraguay soy v1.2.6**
- **Trase SEI-PCS Paraguay beef v1.2.4**

Data retrieved from: [https://www.trase.earth](https://www.trase.earth)  
The data contains firm-level export records, land-use estimates, and destination country details.

## Reproducibility

All code is written in Python and executed in Jupyter Notebooks.  
To reproduce the analysis:

1. Clone this repository.
2. Place raw `.csv` files in a `/data` directory.
3. Run the notebooks in order.

Required libraries:
```bash
pandas
networkx
community
matplotlib
numpy
```

To install dependencies, run:
```bash
pip install -r requirements.txt
```

## Reference

This work was developed as part of the master's thesis:
- **Title:** *Structures, réseaux et pouvoir dans l’économie paraguayenne contemporaine*  
- **Author:** Sergio Rojas  
- **Date:** June 2025  
- **Institution:** Université Paris-Saclay – École normale supérieure Paris-Saclay - UVSQ | Institut Polytechnique de Paris – ENSAE

## Contact

For suggestions, corrections or collaboration inquiries, please contact:  
**Sergio Rojas** – rojasergio6@gmail.com

## License

This work is licensed under the Creative Commons Attribution 4.0 International License.
