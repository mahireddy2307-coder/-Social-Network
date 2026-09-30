# SocialConnect - Friend Suggestion System | ADSA Project

**Student:** Mamillapalli Mahalakshmi
**Subject:** Advanced Data Structures and Algorithms (ADSA)
**Live Demo:** https://mahireddy2307-coder.github.io/social-network-adsa/

## 1. Objective
To design a social network graph and implement friend suggestion and shortest path features using graph algorithms, similar to Facebook / Instagram.

## 2. Data Structures Used (For Viva)

| Feature | Data Structure Used | Why Used |
| :--- | :--- | :--- |
| Store Users & Friends | **Graph - Adjacency List** using HashMap | Efficient storage. `graph = { user: [friends] }`. O(1) to add user |
| Store Friend List | **HashSet** | To avoid duplicate friends and fast lookup |
| Friend Suggestion | **HashMap + Sorting (Max-Heap Logic)** | Count mutual friends, rank by max count |
| Shortest Path (Degrees) | **Queue (BFS - Breadth First Search)** | Finds shortest connection between two users |

## 3. Core Algorithms Explained

**A) Friend Suggestion (Mutual Friends Logic):**
1. For user U, get all friends F.
2. For each friend f in F, get their friends (Friends of Friends).
3. If Friends of Friends is not already a friend of U and not U itself, increase mutual count.
4. Sort by mutual count in descending order - highest mutual friend on top.

**Example:** Maha is friends with Sushu. Sushu is friends with Raju.
-> Raju will be suggested to Maha (1 mutual friend: Sushu)

**B) Shortest Path - Degrees of Separation (BFS):**
Uses Queue. Starts from source user, explores level by level until target is found. Parent map stores path. This gives minimum number of connections between two users.
Time Complexity: O(V + E) where V=users, E=friendships

## 4. Features
1. Add User - Adds node to graph
2. Add Friendship - Adds undirected edge
3. Live Network View - Shows all users and connections
4. Friend Suggestions - Based on mutual friends count
5. Shortest Path (BFS) - Shows degrees of separation

## 5. Time Complexity
- Add User: O(1)
- Add Friendship: O(1)
- Friend Suggestion: O(F * F) where F is avg friends
- Shortest Path (BFS): O(V + E)

## 6. Tech Stack
HTML, CSS, JavaScript (No backend needed, hosted on GitHub Pages)

## 7. How to Run
Just open `index.html` in browser. No installation needed.

## 8. Future Scope
- Community Detection using DFS
- Add weights to friendships (Close Friend)
- Use Dijkstra for weighted suggestions
