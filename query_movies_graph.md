1. Find the actor named "Tom Hanks"...
neo4j$ MATCH (tom {name: "Tom Hanks"}) RETURN tom

2. Find the movie with title "Cloud Atlas"
neo4j$ MATCH (cloudAtlas {title: "Cloud Atlas"}) RETURN cloudAtlas

3. Find 10 people..(sin filtro)
neo4j$ MATCH (people:Person) RETURN people.name LIMIT 10

4. Find movies released in the 1990s...
neo4h$ MATCH (nineties:Movie) WHERE nineties.released >= 1990 AND nineties.released < 2000 RETURN nineties.title

5. List all Tom Hanks movies...
MATCH (tom:Person {name: "Tom Hanks"})-[:ACTED_IN]->(tomHanksMovies) RETURN tom,tomHanksMovies

6. Who directed "Cloud Atlas"?
MATCH (cloudAtlas {title: "Cloud Atlas"})<-[:DIRECTED]-(directors) RETURN directors.name

7.- How people are related to "Cloud Atlas"...
MATCH (people:Person)-[relatedTo]-(:Movie {title: "Cloud Atlas"}) RETURN people.name, Type(relatedTo), relatedTo

8. Movies and actors up to 4 "hops" away from Kevin Bacon
neoj4$ MATCH (bacon:Person {name:"Kevin Bacon"})-[*1..4]-(hollywood)
RETURN DISTINCT hollywood

9. Bacon path, the shortest path of any relationships to Meg Ryan
neoj4$ MATCH p=shortestPath( (bacon:Person {name:"Kevin Bacon"})-[*]-(meg:Person {name:"Meg Ryan"})) RETURN p

10. Extend Tom Hanks co-actors, to find co-co-actors who haven't worked with Tom Hanks.
neo4j$ MATCH (tom:Person {name:"Tom Hanks"})-[:ACTED_IN]->(m)<-[:ACTED_IN]-(coActors),
  (coActors)-[:ACTED_IN]->(m2)<-[:ACTED_IN]-(cocoActors)
WHERE NOT (tom)-[:ACTED_IN]->()<-[:ACTED_IN]-(cocoActors) AND tom <> cocoActors
RETURN cocoActors.name AS Recommended, count(*) AS Strength ORDER BY Strength DESC

11. Find someone to introduce Tom Hanks to Tom Cruise
neo4j$ MATCH (tom:Person {name:"Tom Hanks"})-[:ACTED_IN]->(m)<-[:ACTED_IN]-(coActors), 
(coActors)-[:ACTED_IN]->(m2)<-[:ACTED_IN]-(cruise:Person {name:"Tom Cruise"}) RETURN tom, m, coActors, m2, cruise

Clean up. When you're done experimenting, you can remove the movie data set.
Note: Nodes can't be deleted if relationships exist
Delete both nodes and relationships together
WARNING: This will remove all Person and Movie nodes!

12. Delete all Movie and Person nodes, and their relationships
neo4j$ MATCH (n) DETACH DELETE n

13. Prove that the Movie Graph is gone
MATCH (n) RETURN n

