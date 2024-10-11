# Music Ontology Project

## Project Overview
This project involves the construction of an ontology that describes the domain of music tracks. The ontology is designed to be syntactically and semantically correct, aligning with a knowledge graph built in the [first project](first). It incorporates essential concepts (e.g., songs, composers) and relationships (e.g., genre, creation date) using OWL and the owlready2 Python library for representation.

## Implementation Breakdown
### Part 1: Converting Knowledge Graph to OWL Ontology
This step includes defining classes, properties, and individuals based on the knowledge graph while ensuring syntactical correctness.

- **Initializing Concepts (CN)**

  In this phase, we define the necessary concepts for the ontology. Every individual in the domain is associated with a type, represented as an OWL class. For example, Song and Composer are two essential concepts in the domain, representing individual tracks and their creators, respectively. These concepts are subclasses of the general OWL class, `Thing`.

- **Initializing Relationships (RN)**

  Next, we define the relationships between individuals, representing the properties in the knowledge graph. Two types of relationships are defined:

    - ObjectProperties: These connect individuals (e.g., a song's genre or a composer's country of birth).
    - DataProperties: These connect individuals with data types (e.g., a song's title or duration).

  **Note** : Relationships (RN) do **not** associate individuals (IN) with concepts (CN), this is done via the `rdfs:type` relationship

- **Creating a Semantically Correct Ontology**

  The ontology initially generated from the knowledge graph may be syntactically correct but might not reflect real-world semantics. In this step, we review and modify our model to ensure semantic correctness. For instance, instead of linking songs to genres as individuals, we model genres as subclasses of songs (e.g., RockSong is a subclass of Song).

### Part 2: Ensuring Consistency and Enrichment
This includes ensuring semantic consistency, refining modeling choices, and enriching the ontology with new concepts, roles, and constraints to make the model more robust. In this part of the project we will wor with [Protégé](https://protege.stanford.edu/).

- **Semantic Consistency**

  To ensure the ontology is consistent with real-world constraints, we define domain and range restrictions for each property. Additionally, we define disjoint classes and disjoint roles to ensure that no individual belongs to conflicting classes or roles.

- **Ontology Enrichment**

  In this phase, the ontology is enriched with additional concepts, roles, and axioms, making it more comprehensive and complete. We made sure the ontology we built is both useful and practical for applications like a music recommender or a streaming platform. To do this, we created concepts, roles, and axioms that help the system categorize and recommend music in ways that are meaningful to users.

### Part 3: Enriched Ontology and Data
In this part we worked with a triplestore and more specifically with [GraphDB](https://graphdb.ontotext.com/), where we loaded the [enriched ontology](second/output/myonto-graphDB.owl) we created in Protégé in Part 2, as well as the [enriched knowledge graph](second/output/KR-Ex2_1.owl) we created in Part 1. We then run a reasoner to apply all the rules defined in our ontology. This will enrich our data with types and roles, allowing us to query the ontology using SPARQL and validate the correctness and enrichment of our model.

## Final Output Files
- `myonto-graphDB.owl` :  The ontology we created in the protegé.
- `KR-Ex2_1.owl`: The final ontology in OWL format after applying all refinements and enrichments.

## Conclusions
This ontology project aims to create a solid foundation for representing and understanding the music domain in a structured, semantic way. By following the OWL standards and ensuring both syntactic and semantic correctness, this project can serve as a valuable tool for applications requiring a detailed understanding of music data.
