# The benchmark queries used for PAIRPQ

The prefixes used:

```SPARQL
PREFIX ub: <http://www.lehigh.edu/~zhp2/2004/0401/univ-bench.owl#>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX dbo: <http://dbpedia.org/ontology/>
```



## 1. LUBM data sets

The 8 benchmark queries for PAIRPQ on [LUBM](http://swat.cse.lehigh.edu/projects/lubm/):



1. Q1

   ```SPARQL
   SELECT * WHERE {
   	?x ub:publicationAuthor/ub:advisor ?y.
   }
   ```

2. Q2

   ```SPARQL
   SELECT * WHERE {
   	?x rdf:type ub:Publication.
       ?x ub:publicationAuthor/ub:advisor ?y.
   }
   ```

3. Q3

   ```SPARQL
   SELECT * WHERE {
   	?x ub:publicationAuthor/ub:advisor
          /ub:undergraduateDegreeFrom ?y.
   }
   ```

4. Q4

   ```SPARQL
   SELECT * WHERE {
   	?x ub:publicationAuthor/ub:advisor
          /ub:worksFor ?y.
   }
   ```

5. Q5

   ```SPARQL
   SELECT * WHERE {
   	?x ub:publicationAuthor/ub:advisor
          /ub:name ?y.
   }
   ```

6. Q6

   ```SPARQL
   SELECT * WHERE { 
   	?x ub:worksFor/ub:subOrganizationOf+ ?y.
   }
   ```

7. Q7

   ```SPARQL
   SELECT * WHERE { 
   	?x ub:publicationAuthor/ub:advisor/
          (ub:undergraduateDegreeFrom|ub:teacherOf) ?y
   }
   ```

8. Q8

   ```SPARQL
   SELECT * WHERE { 
   	?x ub:publicationAuthor/ub:advisor+ ?y
   }
   ```



## 2. DBpedia data sets

The 8 benchmark queries for PAIRPQ on [DBpedia](https://www.dbpedia.org/):



   1. Q1

      ```SPARQL
      SELECT * WHERE {
      	?x dbo:birthPlace / dbo:isPartOf ?y
      }
      ```

   2. Q2

      ```SPARQL
      SELECT * WHERE {
          ?x dbo:starring / dbo:birthPlace / dbo:isPartOf ?y
      }
      ```

   3. Q3

      ```SPARQL
      SELECT * WHERE {
          ?x rdf:type dbo:Athlete.
          ?x dbo:birthPlace / dbo:isPartOf ?y.
      }
      ```

   4. Q4

      ```SPARQL
      SELECT * WHERE {
          ?x dbo:birthPlace / dbo:isPartOf / dbo:knownFor ?y
      }
      ```

   5. Q5

      ```SPARQL
      SELECT * WHERE {
          ?x dbo:birthPlace / dbo:isPartOf / dbo:comment ?y
      }
      ```

   6. Q6

      ```SPARQL
      SELECT * WHERE {
          ?x dbo:isPartOf / dbo:knownFor + ?y
      }
      ```

   7. Q7

      ```SPARQL
      SELECT * WHERE {
          ?x dbo:isPartOf / dbo:isPartOf (dbo:isPartOf | dbo:country) ?y
      }
      ```

   8. Q8

       ```SPARQL
       SELECT * WHERE {
          ?x dbo:birthPlace / dbo:country ?y
      }
      ```
