
Source: https://github.com/neo4j-graph-examples/recommendations/blob/main/data/recommendations-43.dump

export (Movie) Nodes
```cypher
WITH "MATCH(n:Movie)
RETURN n.movieId AS movieId, 
    n.tmdbId AS tmdbId,
    //n.languages AS languages, 
    n.year AS year, 
    n.imdbId AS imdbId, 
    n.runtime AS runtime, 
    n.imdbRating AS imdbRating, 
    //n.countries AS countries, 
    n.imdbVotes AS imdbVotes, 
    n.title AS title, 
    n.url AS url, 
    n.revenue AS revenue, 
    n.plot AS plot, 
    n.poster AS poster, 
    n.released AS released,
    n.budget AS budget" AS query
CALL apoc.export.csv.query(query, 'movies.csv', {stream: true})
YIELD file, nodes, relationships, properties, data
RETURN file, nodes, relationships, properties, data;
```

export (Actor)-[:ACTED_IN]->(Movie {movieId})
```cypher
WITH "MATCH(a:Actor)-[:ACTED_IN]->(m:Movie)
RETURN a.tmdbId AS tmdbId,
    m.movieId AS actedInMovieId,
    a.bornIn AS bornIn, 
    a.imdbId AS imdbId, 
    a.born AS born, 
    a.name AS name, 
    //a.bio AS bio, 
    a.died AS died, 
    a.poster AS poster, 
    a.url AS url" AS query
CALL apoc.export.csv.query(query, 'actor-roles.csv', {stream: true})
YIELD file, nodes, relationships, properties, data
RETURN file, nodes, relationships, properties, data;
```

export "ratings" (User)-[:RATED]->(Movie {movieId})
```cypher
WITH "MATCH (u:User)-[r:RATED]->(m:Movie)
RETURN  u.name AS userName, u.userId AS userId, r.rating AS rating, m.movieId AS movieId" AS query
CALL apoc.export.csv.query(query, 'user-ratings.csv', {stream: true})
YIELD file, nodes, relationships, properties, data
RETURN file, nodes, relationships, properties, data;
```
