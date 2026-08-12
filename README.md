# Skill Network 
A graph-based web application built using **Java Servlets, JSP, CSS, and CognoDB (Neo4j-compatible graph database)**. 

## Why a graph database? This application models **people and their skills** as connected entities: - Person → HAS_SKILL → Skill - Skill ← HAS_SKILL ← Person Graph traversal makes it easy to discover people connected through shared skills, which is more natural than complex SQL joins. 

## Data Model (Person)-[:HAS_SKILL]->(Skill) ## Features - Add a person - Add a skill to a person - Search people connected by a skill - View all people and their skills

## Project Structure - Java Servlets - JSP pages - CSS styling - Cypher schema and seed scripts - Maven project 

## Main Query (Multi-hop Traversal) MATCH (p1:Person)-[:HAS_SKILL]->(s:Skill)<-[:HAS_SKILL]-(p2:Person) WHERE s.name = $skill AND p1.name <> p2.name RETURN p1.name, p2.name, s.name 

## Screenshots ### Home Page ![Home](screenshots/home.png)

### People and Skills ![People](screenshots/people.png) 

### Project Structure ![Structure](screenshots/structure.png) ## Setup 1. Create a CognoDB instance. 2. Configure environment variables. 3. Run `schema.cypher`. 4. Run `seed.cypher`.

5. Deploy on Tomcat and open: http://localhost:8082/SkillNetwork/ ## Screen Recording Add your video link here. ## Author Karthik K
