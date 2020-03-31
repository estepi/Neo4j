# Neo4j
This repository contains useful scripts to work with a Neo4J DB
First steps with Neo4j in Linux Ubuntu 18.04  (Desktop version)
1.  Download 

Installation and Launch Guide
https://neo4j.com/download-thanks-desktop-b/?edition=desktop&flavour=unix&release=1.2.5&offline=true#installation-guide

* Step 1: Make the file executable
Locate the AppImage file of Neo4j Desktop you just downloaded.
Make the file executable by running the following command chmod +x FILE_NAME

* Step 2: Run the file. Now you can double click on the downloaded file to open Neo4j Desktop.

** Step 1: Activation: Copy and Paste the activation at the top of this page in the "Activation Key" box in the Neo4j Desktop app. Alternatively, you can also generate a key from within the app by filling out the form on the right side of the app screen.

** Step 2: Create a database. After activation, click on the "New Graph" buton. Select "Create a local graph" from the options presented. Next, enter the "Database name" and "Password" in field and click on the "Create" button.
More information about installation on Linux/Ubuntu is available here
(in my case DB Name. EX, password: exons

** Step 1: Start Neo4j Browser. After the database starts, click on the "Manage" button.
On the next screen, locate "Open Browser" on top of the screen and click on it. This will open Neo4j Browser in a new window.

** Step 2: Explore sample dataset. 
Neo4j Desktop comes with two sample datasets. You can run them using the following commands (Cypher)
:play movie graph 
:play northwind graph



Learn more about how to use Neo4j Browser here.
3.  Populate
4.  Play

Interested in:
* Bloom 
* Linkurius (ogma)
* Populate
* Different layers
* Different Metrics
* Visualization according connectivity metrics

In parallel, comunity release:
* Download from: https://neo4j.com/download-center/
** Version: neo4j-community-3.5.17-unix.tar.gz
* Download apoc from: https://github.com/neo4j-contrib/neo4j-apoc-procedures
(put in plugis folder)

* Configure Neo4J
* Import data (use: 

