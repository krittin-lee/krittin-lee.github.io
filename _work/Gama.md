---
layout: work
title: "CUPS (w/ Gama Platform)"
description: "Chulalongkorn University campus Pedestrian Silumation with Gama Platform"
image: "/assets/arts/Banner_CUPS.jpeg"
year: "2026"
role:
emoji: "🚸"
month_season: "November"
for:
team:
advisors: 
tool: 
order: "7"  
display: true
---
# Chulalongkorn University campus Pedestrian Silumation (CUPS)

CUPS is an agent-based pedestrian movement simulation developed in **[GAMA Platform](https://gama-platform.org)**, using Chulalongkorn University’s campus as a real-world spatial environment. The project explores how individual pedestrians navigate a complex campus environment and how their collective movement forms broader patterns of mobility. By representing pedestrians as autonomous agents with individual starting positions, walking speeds, and destinations, the simulation provides a computational way to investigate pedestrian distribution, route selection, and spatial connectivity.

A key foundation of the project is geographic data from **[OpenStreetMap (OSM)](https://www.openstreetmap.org/)**, a collaborative, open geographic database maintained by a global community of contributors. Building footprints and road geometries are extracted from OSM and processed into shapefiles for use in GAMA Platform. This approach makes use of openly available, community-maintained spatial data rather than relying solely on manually constructed environments. It also demonstrates how volunteered geographic information can serve as the foundation for more complex urban analysis and simulation.

<figure style="max-width: 560px; width: 50%; margin: 0 auto 20px auto;">
	<img src="https://upload.wikimedia.org/wikipedia/commons/c/c9/Chulalongkorn_University_Auditorium_High_View.JPG?utm_source=commons.wikimedia.org&utm_campaign=index&utm_content=original" alt="Chulalongkorn University campus view form above.">
	<figcaption class="image-subtitle">A view of Chulalongkorn University campus from above. Credit: Tangmo~commonswiki (CC BY-SA 3.0) form<a href="https://commons.wikimedia.org/wiki/File:Chulalongkorn_University_Auditorium_High_View.JPG">Wikimedia Commons</a>.</figcaption>
</figure>

Within GAMA, the geographic features are translated into a spatial environment and a graph-based road network through which pedestrian agents can move. The current model experiments with directing agents towards a shared destination, providing a basis for examining how the layout and connectivity of campus pathways influence movement. By bringing together OpenStreetMap data, GIS processing, network modelling, and agent-based simulation, ChulaPedestrianMRT explores the potential of open geographic data to support the study of everyday human mobility.<br>[See the sourcecode](https://github.com/krittin-lee/Gama-Chula-Testing)