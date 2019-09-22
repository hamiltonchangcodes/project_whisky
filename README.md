# project_whisky

Welcome to Project Whisky.  In this project, we will be attempting to classify whiskies by their country of origin based on their flavor profile, ingredient type, and whiskey type.

## Data

Data is sourced from Whiskeyanalysis.com.  Data consisted of 1600 individual whiskies, and ranged from the following:

Target:   
Countries - Scotland, USA, Canada, Ireland, Japan, Sweden, India, Taiwan, Wales, Switzerland, Finland, Tasmania, South Africa, Netherlands, England, Belgium, France.  
Features:  
Cluster: A, B, C, D, E, F, G, H, I, J, R0, R1, R2, R4.  
Class - Single-Malt like, Blend, Rye-like, Bourbon-like.   
Type - Malt, Blend, Grain, Rye, Wheat, Barley, Bourbon, Flavored

EDA

Initial problems I encountered were in properly classifying my data.  I first needed to convert countries into number values, which was a simple replace.  Due to the massive imbalance between Scotch whiskies and the whiskies produced from the rest of the world, I also grouped the 11 least populous whiskies and grouped them as "rest_of_world," keeping Scotland, USA, Canada, Ireland, and Japan.
Prior to reorganizing, countries were broken up into the following:
<img src="Images/country_graph.png">
In addition, the original dataset creator chose to rank Bourbons based on their Rye content, as bourbon tends to follow a set flavor characteristic, and is particularly distinguishable by its rye content, which gives rye whiskies its distinctive "spiciness."  In order to better train the model and avoid automatically identifying "R's" as bourbon, I needed to translate the "R's" into a more streamlined format based on the general flavor profile of bourbons based on the pre-existing flavor categories, taking spiciness into account.  Thus the final transformation was lined up thusly:

RO = B
R1 = A
R2 = E
R3 = C
R4 = F

