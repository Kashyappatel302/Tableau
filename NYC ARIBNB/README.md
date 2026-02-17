NYC Airbnb Listings Analysis
An interactive Tableau dashboard analyzing 49,000+ Airbnb listings across New York City's five boroughs. The project explores pricing patterns, geographic 
distribution, room type composition, seasonal demand, and host concentration to surface actionable insights for hosts, investors, and city regulators.

Dashboard Preview:- https://public.tableau.com/views/NYCAIRBNBLISTINGANALYSIS/Dashboard1?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link

Objective
Analyze NYC Airbnb data to understand how listing prices, room types, availability, and booking activity vary across boroughs and neighborhoods, identify 
commercial-scale host operations, detect seasonal demand patterns, and deliver insights relevant to pricing strategy, market entry decisions, and regulatory 
assessment.

Dataset
Source: New York City Airbnb Open Data — Kaggle
The dataset contains approximately 49,000 individual Airbnb listings from 2019. Each row represents a single listing and includes host information, borough 
and neighborhood location, latitude and longitude coordinates, room type (Entire home/apt, Private room, Shared room), nightly price, minimum nights required, 
review counts and dates, reviews per month, the host's total listing count, and availability measured in days per year. Roughly 20% of rows have null values 
in the last_review and reviews_per_month fields, representing listings that have never been reviewed.

Data Cleaning and Preparation
The raw dataset required several preparation steps handled directly within Tableau. A data source filter was applied to exclude listings priced at $0 
(data errors) and above $1,000 per night (extreme outliers that would distort averages). Null values in review-related fields were retained for geographic 
and pricing analysis but naturally excluded from time-based charts. Four calculated fields were created to enrich the analysis: a Price Category field binning 
prices into five tiers (Budget, Mid-Range, Upper Mid, Premium, Luxury) using conditional logic, an Availability Status field categorizing listings by days open 
per year, a flag for highly reviewed listings (50+ reviews), and a Revenue Estimate field multiplying nightly price by presumed booked days as a rough annual 
earnings proxy.

Dashboard Components
The dashboard consists of seven interconnected views assembled into a structured layout.
A geographic scatter map plots all 49,000 listings using raw latitude and longitude, colored by borough with reduced opacity and small point sizes to manage 
the density of overlapping points. A price density heatmap uses Tableau's density mark type weighted by average price to show where expensive listings cluster 
geographically. A horizontal bar chart displays average nightly price for the top 20 most expensive neighborhoods using a Top N filter, colored by borough, 
with listing count in tooltips to prevent misleading interpretations from low-volume neighborhoods. A room type distribution chart shows the percentage 
breakdown across Entire home/apt, Private room, and Shared room. A review activity line chart tracks listing counts by last review date on a continuous 
monthly axis as a proxy for seasonal booking volume. An availability highlight table presents a Borough by Room Type matrix with average availability mapped 
to color intensity. A top hosts bar chart identifies the 15 hosts with the most listings to reveal commercial-scale operators.
Three global filters (Borough, Room Type, Price Category) apply across all sheets. Filter actions enable clicking a borough cluster on the map to update 
all charts, and clicking a neighborhood bar to highlight those listings on the map. Hover-based highlighting provides softer cross-chart interaction. A 
consistent color palette is maintained across all views for both borough and room type encodings.

Key Findings
Manhattan and Brooklyn together account for roughly 75% of all NYC Airbnb listings, with Manhattan neighborhoods like Tribeca, SoHo, and NoHo averaging 
over $200 per night. Entire home/apt listings make up approximately 52% of the market, Private rooms about 46%, and Shared rooms just 2.4%, showing the 
platform tilts heavily toward full-unit rentals. Review activity shows a sharp seasonal pattern with June–July peaks and January–February dips, reflecting 
the city's tourism cycle. Several hosts manage over 100 listings each, suggesting commercial property management operations rather than individual room 
sharing. Staten Island shows the highest average availability but lowest booking activity, consistent with its distance from tourist centers. Some top-priced 
neighborhoods have fewer than 10 listings, making their averages unreliable without volume context.

Recommendations
Hosts in outer boroughs should benchmark pricing against Manhattan competitors by room type rather than relying on local neighborhood averages alone. The 
June–July demand spike represents the optimal window for new hosts to list and capture peak bookings. City regulators may want to investigate hosts with 
50+ listings as potential commercial hotel operations that could fall outside home-sharing regulations. Investors evaluating short-term rental potential 
should combine the Revenue Estimate proxy with availability data rather than relying on nightly price alone, since high price with low availability generates 
less revenue than moderate price with high occupancy.

Tools and Techniques
Tableau Public was used for all data cleaning, analysis, visualization, and dashboard publishing. Data preparation included outlier filtering at the data source 
level, null handling, and four custom calculated fields using conditional logic and arithmetic expressions. Visualization types used include geographic scatter 
maps with raw lat/long coordinates, density heatmaps, horizontal bar charts with Top N filtering, pie charts with percentage table calculations, time-series 
line charts with continuous date axes, and highlight tables with color-encoded matrices. Dashboard interactivity was built using global dropdown filters, 
click-based filter actions between the map and charts, and hover-based highlight actions. The project applies concepts from exploratory data analysis, geospatial 
visualization, KPI design, interactive dashboard development, and data storytelling.
