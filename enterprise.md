Download Enterprise Version
1. https://neo4j.com/download-center/#enterprise

Ahroa arranco con Cypher:2
. ./bin/neo4j-admin set-initial-password demo
 chequear en  que se haya creado la dbms
 
3. Start:
./bin/neo4j start

Started neo4j (pid 14839). It is available at http://localhost:7474/
There may be a short delay until the server is ready.

4.- Aca esta el log del servicio:
tail -f logs/neo4j.log

5.- Abrir el browser
http://localhost:7474/browser/

6. Tengo que autentificar con el user/pass que confirgure: user neo4j, pass demo

Ahroa arranco con Cypher:
7.:use system
Use database: You have updated what database to use in the Neo4j dbms. 
show databases
create database db1
create database db2
show databases

* Nota Se guardaran aca: ~/Documents/neoE/neo4j-enterprise-4.0.3/data/databases

8. Fabric: Neo4j Fabric (para que era esto??)
 Editar conf/neo4j.conf:

fabric.database.name=example
fabric.graph.0.uri=neo4j://localhost:7687
fabric.graph.0.name=graphA
fabric.graph.0.database=db1
fabric.graph.1.uri=neo4j://localhost:7687
fabric.graph.1.name=graphB
fabric.graph.1.database=db2



9. Cargar datos:
:use db1
:play movie-graph
(navigate pagina 2)
(ejecutar cypher)



