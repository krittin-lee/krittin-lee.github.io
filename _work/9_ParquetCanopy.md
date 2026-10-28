---
layout: work
title: "★★★ ParquetCanopy"
description: "Geospatial data integration for forest-risk analysis."
image: "assets/ParquetCanopy/internship cover.jpg"
year: "2025"
role: "Data engineer, back-end develper"
emoji: "🌳"
month_season: "Summer"
for: "Internship at i-bitz Company Limited"
team: 
advisors: "Prasong Patheepphoemphong (CEO), Pongsakorn Udombua (CTO)" 
tool:   
order: "9"  
---
# ParquetCanopy
## Making Different Maps Work Together

*Forests do not follow file formats, administrative boundaries, or coordinate reference systems. Geospatial software has to deal with all three.*

A forest-risk assessment may begin with a map, but the data behind that map rarely comes from a single source. National agencies publish administrative boundaries. International organizations maintain databases of protected areas. Satellite-derived products describe forest cover through raster grids, while other datasets represent the same landscape as polygons.

Each source has its own purpose, structure, spatial reference, and definition of what it represents.

ParquetCanopy is a geospatial data service built with FastAPI, DuckDB, and Parquet. The project explores how heterogeneous geographical datasets can be organized into a queryable system for forest monitoring and deforestation-risk assessment, particularly in the context of the European Union Deforestation Regulation (EUDR).

The difficult part is not putting these datasets on the same screen. It is making them meaningfully comparable without losing the information that makes each one useful.

---

## The Problem Is Not a Lack of Maps

<figure>
	<img src="assets/ParquetCanopy/different formats.jpg" alt="Data in different formats">
</figure>

Deforestation is a physical process, but identifying and documenting it requires information from several different systems. The Food and Agriculture Organization of the United Nations estimated that approximately 10 million hectares of forest were deforested annually between 2015 and 2020.[^1] Understanding where forest loss occurs, and how it relates to agricultural production and land-use restrictions, requires more than a single representation of the landscape.

One dataset may describe forest cover. Another may identify a national park. A third may define a national reserved forest. An international database may contain a separate boundary for a protected area covering some or all of the same land. As these layers are related, but they are not interchangeable.

A national park boundary is a legal or administrative designation. A forest-cover map represents a classification of land. A protected-area database aggregates information from different jurisdictions and providers. Even where two boundaries overlap, they may represent different legal categories, source dates, or mapping methodologies.

The resulting challenge is one of geographical interoperability: determining how to work with these representations together while preserving their differences. The objective is not to make every dataset identical. It is to make their differences explicit and their relationships computable.

## EUDR: From Commodity Supply Chains to Geographical Evidence

<figure>
	<img src="assets/ParquetCanopy/EUDR.jpg" alt="Data in different formats">
</figure>

The European Union Deforestation Regulation, formally Regulation (EU) 2023/1115, addresses the relationship between commodity supply chains and deforestation. It covers cattle, cocoa, coffee, oil palm, rubber, soy, and wood, together with specified products derived from them.[^2]

The regulation requires relevant products placed on the EU market or exported from it to satisfy deforestation-free and legality requirements, supported by due diligence.

Geography is central to this process. Operators must collect geolocation information for the plots of land where relevant commodities were produced. The regulation's definition of deforestation-free uses a cutoff date of 31 December 2020.[^2]

These requirements turn a seemingly simple question – where was this commodity produced? – into a geographical investigation.

A production plot can be compared with forest-cover data, historical land-cover observations, and relevant protected-area boundaries. Those comparisons can help identify locations requiring additional investigation.

However, the presence of a plot inside a mapped forest or protected area does not automatically establish an EUDR violation. Nor does its absence from one particular dataset establish compliance. Maps are evidence inputs, not substitutes for the complete due-diligence process.

For ParquetCanopy, EUDR provides the wider context for investigating how forest-related geographical data can be assembled, queried, and made available for further analysis.

## References

[^1]: Food and Agriculture Organization of the United Nations (FAO). *Global Forest Resources Assessment 2020.* [Read the report](https://www.fao.org/interactive/forest-resources-assessment/2020/en/).

[^2]: European Union. *Regulation (EU) 2023/1115 on deforestation-free products.* [Read the regulation](https://eur-lex.europa.eu/eli/reg/2023/1115/oj).