# Portfolio Information

Course Name: Algorithmic Problem Solving  
Course Code: 23ECSE309  
Name: Shashidhar Angadi  
SRN: 01fe21bec275  
Course Instructor: Prakash Hegade  
Portfolio Topic/Domain: Spotify

# Spotify Portfolio

---

## Objectives

This portfolio highlights my expertise in leveraging advanced algorithms and data structures within the Spotify ecosystem. Key objectives include demonstrating proficiency in developing efficient solutions for music recommendation, playlist generation, data analysis, and user management. Each project showcases the application of theoretical concepts in practical settings, emphasizing innovation and optimization within Spotify's dynamic platform.

## Introduction

Welcome to my Spotify portfolio! This website serves as a showcase of my skills and projects within the Spotify ecosystem. As a software developer with a passion for music and technology, I've chosen Spotify for its influential role in music streaming and its robust platform for algorithmic development. Spotify not only enriches the listening experience but also provides an ideal environment to apply cutting-edge algorithms and data structures.

## Why Spotify?

Spotify's platform offers a rich environment for software developers to innovate and enhance user experiences through data-driven solutions. From personalized recommendations to real-time data analytics, Spotify provides ample opportunities to integrate advanced algorithms and optimize performance.

## System Design

<p align="center">
  <img src="https://miro.medium.com/v2/resize:fit:1400/format:webp/1*FNqvivFHngTauwsFphWXQA.png" width="500" alt="system design">
</p>

### Initial Phase: Base Version

Requirements: The initial requirement for this phase is to handle 500k users and 30M songs. Users interact with songs through a mobile app, playing and creating playlists. Artists upload songs.

Estimation: Data Math

To meet storage needs:
- Song Storage: Assuming an average song size of 3MB, we need 90TB of storage.
- Song Metadata: Approximately 3GB for metadata.
- User Metadata: About 0.5GB for user data.

### High-Level Design

- Mobile App: Front end for user interaction.
- Load Balancer: Distributes traffic across multiple web servers.
- Web Servers (APIs): Handle requests from the mobile app.

### Data Storage

- Songs: Stored in Blob Storage (e.g., AWS S3, GCP, Azure Blob Storage).
- Users, Artists, and Song Metadata: Stored in a SQL Database (e.g., PostgreSQL, MySQL) for structured data and complex queries.

#### SQL Database Structure

Tables include:
- Users Table: User metadata.
- Songs Table: Song metadata and references to song files.
- Artists Table: Artist information.

#### Data Flow

Web servers retrieve song metadata from the SQL database and stream songs from Blob Storage to users.

### Scaled Phase: 50M users, 200M songs

Recalculation: With 200M songs:
- Song Metadata: Approx. 20GB.
- User Metadata: Approx. 50GB.

### Introducing a CDN

- CDN (Content Delivery Network): Caches songs closer to users for faster access, reducing load on web servers.

### Scaling the Database
<p align="center">
  <img src="https://miro.medium.com/v2/resize:fit:828/format:webp/1*rVoxlvoqbENlbf0ciOIdog.png" width="500" alt="system design">
</p>
- Leader-Follower Technique: One writable leader database and multiple read-only follower databases for scalability.

---

## Spotify Functionalities

### 1. Music Recommendation System

Spotify's recommendation system analyzes user preferences and listening behavior to suggest relevant songs, artists, and playlists.

Functionality: The recommendation system employs collaborative filtering and matrix factorization to personalize user recommendations based on historical listening data.

Data Structure: User-Item Matrix

Algorithm: Collaborative Filtering

Complexity:
- Matrix Construction: O(m * n), where m is the number of users and n is the number of items.
- Recommendation: O(k * log n), where k is the number of recommendations.

 [User-Item Matrix and Collaborative Filtering](https://medium.com/@payalswami/system-design-of-spotify-17b1c828b7bf)
 
### 2. Playlist Generation

Users can create and manage personalized playlists based on their music preferences.

Functionality: Playlist generation uses a linked list data structure to efficiently manage song order and metadata.

Data Structure: Linked List

Algorithm: Greedy Algorithm for Playlist Optimization

Complexity: O(n log n), where n is the number of songs.

- [Linked-list](https://github.com/shashidhar275/shashidhar275.github.io/blob/main/codes/Linked-list)

### 3. Search Functionality

Spotify's search feature enables users to find songs, albums, and artists quickly.

Functionality: Search functionality utilizes an inverted index for full-text search, supporting efficient indexing and querying.

Data Structure: Inverted Index

Algorithm: Inverted Index

Complexity:
- Indexing: O(n log n), where n is the number of documents.
- Querying: O(k + log n), where k is the number of query terms.

[Inverted Index](https://www.geeksforgeeks.org/inverted-index/)

### 4. Streaming and Playback

Spotify provides high-quality music streaming and playback.

Functionality: Streaming employs a queue data structure for adaptive bitrate streaming, ensuring smooth playback across different network conditions.

Data Structure: Queue

Algorithm: Adaptive Bitrate Streaming

Complexity: O(1) per bitrate selection per chunk.

[Queue](https://github.com/shashidhar275/shashidhar275.github.io/blob/main/codes/queue.cpp)

### 5. Social Features

Users can follow friends, share music, and collaborate on playlists.

Functionality: Social features utilize a graph data structure to manage relationships and connections between users.

Data Structure: Graph

Algorithm: BFS/DFS for Connectivity

Complexity: O(V + E), where V is the number of vertices (users) and E is the number of edges (connections).

[BFS](https://github.com/shashidhar275/shashidhar275.github.io/blob/main/codes/BFS.cpp)
[DFS](https://github.com/shashidhar275/shashidhar275.github.io/blob/main/codes/DFS.cpp)

### 6. Data Analysis and Insights

Spotify offers insights into listening habits and trends through data analytics.

Functionality: Data analysis uses time series analysis to identify patterns and trends in user behavior.

Data Structure: Time Series

Algorithm: Time Series Analysis

Complexity: O(n log n) for analyzing trends over time.

[Time Series Analysis](https://medium.com/@majkellveizaj/time-series-analysis-and-forecasting-using-spotify-song-streams-6c724017fc66)

### 7. Notifications

Spotify notifies users about new releases, updates, and recommendations.

Functionality: Notifications employ an event queue data structure for efficient event handling and dispatch.

Data Structure: Event Queue

Algorithm: Event Handling and Dispatch

Complexity: O(1) per event.

 [Event Queue](https://www.geeksforgeeks.org/event-queue-in-javascript/)

### 8. User Management

Spotify manages user accounts, preferences, and authentication.

Functionality: User management uses a hash table for fast account creation, authentication, and secure password storage.

Data Structure: Hash Table

Algorithm: Secure Hashing and Salted Password Storage

Complexity: O(1) (average) for operations like insertion, deletion, and lookup.

[Hash Table](https://www.digitalocean.com/community/tutorials/hash-table-in-c-plus-plus)

### 9. Track Uploading

<p align="center">
  <img src="https://miro.medium.com/v2/resize:fit:828/format:webp/1*YTJ3VHLupy9peG2C6u0PHQ.png" width="500" alt="system design">
</p>

Artists and creators can upload their tracks to Spotify.

Functionality: Track uploading integrates file systems and databases for efficient storage, retrieval, and metadata management.

Data Structure: File System, Database

Algorithm: File Handling and Database Integration

Complexity: - (Specific complexities depend on implementation details of the file system and database used).

### 10. Extended Recommendation Engine

Spotify's advanced recommendation engine incorporates deep learning models for enhanced personalization.

Functionality: The extended recommendation engine utilizes neural networks for collaborative filtering and real-time recommendation updates.

Data Structure: Neural Networks

Algorithm: Neural Collaborative Filtering

Complexity:
- Model Training: Depends on the neural network architecture and dataset size.
- Recommendation: O(k * log n), where k is the number of recommendations.

 [Neural Collaborative Filtering](https://medium.com/data-science-in-your-pocket/recommendation-systems-using-neural-collaborative-filtering-ncf-explained-with-codes-21a97e48a2f7)

---
## References

1. [levelup](https://levelup.gitconnected.com/system-design-interview-question-design-spotify-4a8a79697dda)
2. [Medium](https://medium.com/@payalswami/system-design-of-spotify-17b1c828b7bf)
