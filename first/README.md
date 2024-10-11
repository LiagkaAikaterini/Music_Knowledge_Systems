# Music Recommendation System Using Knowledge Graphs

## Project Overview

This project involves the development of a knowledge graph to power a music recommendation system. he goal is to provide personalized music recommendations by leveraging a rich network of interrelated musical data, representing connections between tracks, artists, albums, genres, and user preferences.

## Implementation Breakdown
### Part 1: Familiarization with the Programming Environment
This section focuses on familiarizing users with the programming environment used for creating and manipulating knowledge graphs. 

It demonstrates how a user can:
- Load a simple RDF graph from a file.
- Perform SPARQL queries to extract information about musical pieces.
- Extend the graph by adding new triples.
- Create a second graph using data from a CSV file, ensuring that it connects to the original graph.
- Merge the two graphs and query them to showcase their interconnectedness.

### Part 2: Knowledge Graph Construction and Querying
In this section, we focus on the **creation of a knowledge graph** that represents the various entities within the music domain, such as: 
- Track Title
- Genres
- Emotions
- Instruments
- Release Year
- Duration
- Composers and additional information about them (such as birthdate, deathdate, biography, music movement, if he has music awards)
- Publishers
- Creation Place
- Language

**Key aspects:**

1. RDF triples are used to define the relationships between these entities.
2. The goal is to form a highly interconnected structure that captures the complex relationships between different music elements, allowing the system to model connections between, for example, an artist and all tracks they’ve composed, or the genre associated with a particular track.
3. This section will also demonstrate how we define these relationships and provide a foundation for the recommendation engine by structuring this rich dataset.

Then we use **SPARQL queries** to extract useful information from the knowledge graph:

We show various queries that allow us to retrieve specific details about the music data, such as:
- All tracks by a given artist.
- Tracks released in a particular year or by a particular publisher.
- Music that matches user preferences based on genres, composers, or other metadata.

The focus here is on showing how the graph is queried to fetch and filter relevant musical data for the recommendation engine, providing the backbone for personalized recommendations.

### Part 3: Recommender System Integration
In the final section, we demonstrate how the knowledge graph is integrated with a music recommendation systems:

- The data from the graph is used to create personalized recommendations based on a user’s listening history, preferences, and behaviors.
- By leveraging the relationships in the graph, the system can offer context-aware suggestions, such as recommending tracks that share the same genre, or albums by artists similar to those the user has enjoyed.
- We highlight how the graph allows for deeper insights, making recommendations more accurate and tailored to individual users.

#### Recommenders
We created 3 distinct recommenders, each with unique criteria for suggesting songs based on user preferences.

**1. _First Recommender_:**
- Suggests songs based on shared characteristics with a given song, such as:
- Same composer or language of the composer.
- Common genres among award-winning composers.
- Similar duration (within a 100-unit difference).
- Same publisher.

**2. _Second Recommender_:**
- Recommends songs that share at least one genre and have composers born within 10 years of each other.
- Suggests songs with the same composer, at least two shared emotions, and a common instrument.
- Matches songs based on the same musical movement as the composer.

**3. _Third Recommender_:**
- Proposes songs with at least one genre in common and similar durations (within a 10-unit difference).
- Identifies songs with at least two shared genres and one emotion.
- Recommends songs with the same publisher released in the same decade.
- Looks for songs that share one genre, one emotion, and two different instruments.

#### Evaluation Metrics
To evaluate the performance of these recommenders, precision and recall metrics are calculated using user preferences from the provided `users.txt` and `new_users.txt` files. The metrics are defined as follows:

- **_Precision:_** The ratio of true positive recommendations to the total predicted recommendations.
- **_Recall:_** The ratio of true positive recommendations to the total number of actual liked songs by the user.

## Conclusions
Together, these three parts outline the entire process—from constructing the knowledge graph and querying it for specific information to using it to power a personalized music recommender system.
