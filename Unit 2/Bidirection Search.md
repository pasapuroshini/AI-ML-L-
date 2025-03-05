**Bidirectional Search Explained from Scratch**
===============================================

### **What is Bidirectional Search?**

Bidirectional Search is an optimization of traditional search algorithms (like BFS and DFS). Instead of searching from the **start node to the goal node in one direction**, it performs **two simultaneous searches**:

1.  **Forward Search:** From the start node toward the goal.
    
2.  **Backward Search:** From the goal node toward the start.These searches continue until their frontiers meet in the middle, forming a path from the start to the goal.
    

This approach significantly **reduces the number of nodes explored**, making it much faster than searching in a single direction.

**Why Use Bidirectional Search?**
---------------------------------

Searching from **both ends** at the same time reduces the total number of nodes generated.

🔹 **Example:** Suppose the solution depth (**d**) is 6, and the branching factor (**b**) is 10.

*   **Breadth-First Search (BFS):** It explores **O(b^d) = O(10^6) = 1,111,110** nodes.
    
*   **Bidirectional Search (BDS):** Each search explores **O(b^(d/2)) = O(10^3) = 2,220** nodes.
    

📌 **Conclusion:** BDS is much faster because **bd/2 + bd/2 ≪ bd**.

**How Bidirectional Search Works**
----------------------------------

1.  **Initialize Two Frontiers:**
    
    *   A queue for **forward search** starting from the initial node.
        
    *   A queue for **backward search** starting from the goal node.
        
2.  **Expand the Frontiers Alternately:**
    
    *   Expand one node from the **forward frontier**.
        
    *   Expand one node from the **backward frontier**.
        
3.  **Check for Intersection:**
    
    *   If a node appears in both searches, the path is found.
        
4.  **Reconstruct the Path:**
    
    *   Combine the forward and backward paths to get the complete solution.
        

**Time Complexity of Bidirectional Search**
-------------------------------------------

*   The worst-case complexity is **O(b^(d/2))**, which is **exponentially smaller** than BFS (**O(b^d)**).
    
*   However, **space complexity is also O(b^(d/2))**, since we store two frontiers in memory.
    

**Challenges in Bidirectional Search**
--------------------------------------

1.  **Finding Predecessors (Backward Search Difficulty):**
    
    *   In **some problems**, defining a "reverse move" is difficult.
        
    *   Example: If you're searching for a path in a city, it's easy to go backward (roads are bidirectional).
        
    *   But in a puzzle like the **N-Queens problem**, defining a "reverse move" is not straightforward.
        
2.  **Multiple Goal States:**
    
    *   If multiple goal states exist, we create a **dummy goal state** that connects to all of them.
        
3.  **Memory Usage:**
    
    *   We must store two frontiers, making **space complexity O(b^(d/2))**, which can still be large.
  
   *   **Bidirectional Search is much faster** than unidirectional search because it searches from both ends.
    
*   **It reduces time complexity to O(b^(d/2))**, making it very efficient for large problems.
    
*   **It requires extra memory** for storing two frontiers, making space complexity O(b^(d/2)).
    
*   **Backward search is sometimes difficult**, especially in problems with irreversible actions.
