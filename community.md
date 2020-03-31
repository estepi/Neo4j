Pasos para trabajar con el community.
Que es el community?

1. Bajar la version community de Neo4J: https://neo4j.com/download-center/

Baje :neo4j-community-3.5.17-unix.tar.gz

2.- En el directorio de plugins, hay que bajar apoc

Place APOC jar in plugins directory:
https://neo4j.com/labs/apoc/
APOC is an add-on library for Neo4j that provides hundreds of procedures and functions adding a lot of useful functionality.

Toni recomienda la 3.5.0.9 : This is a small release, mostly for a feature addition for a new integration.
https://github.com/neo4j-contrib/neo4j-apoc-procedures/releases/tag/3.5.0.9
https://github.com/neo4j-contrib/neo4j-apoc-procedures


3. Editar el file neo4j.conf
Descomentar esta linea
dbms.security.procedures.whitelist=apoc.coll.*,apoc.load.*

4. Importar los datos con el script de importacion
bash run.sh /home/estepi/Documents/website/neo4j-community-3.5.17/bin/cypher-shell /home/estepi/Documents/website/labvalcarcel-spliceosome-master/neo4j/data/classification_final.csv /home/estepi/Documents/website/labvalcarcel-spliceosome-master/neo4j/data/types /home/estepi/Documents/website/labvalcarcel-spliceosome-master/neo4j/data/Source_Event_Targe





