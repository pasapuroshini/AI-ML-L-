### **Understanding Search in Problem-Solving Agents**

When solving a problem, an agent must explore different possible **sequences of actions**. This process is called **search**, and it is represented using a **search tree**.

### **1\. Search Tree**

*   The **root node** represents the **initial state** (e.g., _In(Arad)_).
    
*   **Branches** represent possible actions the agent can take.
    
*   **Nodes** in the tree represent **states** in the **state space**.
    
*   The **goal is to find a path** from the initial state to the goal state (_In(Bucharest)_).
    
*   The **search tree grows** as the agent expands nodes (i.e., explores possible actions).
    

### **2\. Expanding a Node**

*   **Expanding** a node means applying all **legal actions** to generate new states.
    
*   Example:
    
    *   The agent starts in _In(Arad)_.
        
    *   The possible actions: {Go(Sibiu), Go(Timisoara), Go(Zerind)}.
        
    *   The new states are {In(Sibiu), In(Timisoara), In(Zerind)}.
        

### **3\. Choosing Which Node to Expand Next**

*   **The search strategy determines which node to expand next**.
    
*   The agent **picks one state**, expands it, and **adds the new states to the frontier**.
    
*   Example:
    
    *   If the agent picks _Sibiu_ first, it generates {In(Fagaras), In(Oradea), In(RimnicuVilcea)}.
        

### **4\. The Frontier (Open List)**

*   The **frontier** consists of **all leaf nodes** (states available for expansion).
    
*   **Leaf nodes** have **not yet been expanded**.
    
*   The search continues **until a goal state is found or no nodes remain**.
    

### **5\. Handling Loops and Redundant Paths**

*   **Repeated States (Loopy Paths)**:
    
    *   Example: If the agent moves from _Arad → Sibiu → Arad_, it **revisits Arad**.
        
    *   This creates an **infinite loop** if not handled properly.
        
    *   **Solution**: Track visited states to prevent cycles.
        
*   **Redundant Paths**:
    
    *   Example: _Arad → Sibiu (140 km)_ vs. _Arad → Zerind → Oradea → Sibiu (297 km)_.
        
    *   The second path is **longer and unnecessary**.
        
    *   **Solution**: Always keep the **shortest known path** to a state.
        

### **6\. The TREE-SEARCH Algorithm**

The basic algorithm follows these steps:

1.  Start with the **initial state**.
    
2.  Check if it’s the **goal state** (if yes, return the solution).
    
3.  **Expand** the current state (generate successors).
    
4.  Add new states to the **frontier**.
    
5.  Repeat until the **goal is found** or no nodes remain.
    

### **Conclusion**

*   The **search tree** helps an agent **systematically explore** different paths.
    
*   The **search strategy** determines the **efficiency** of finding a solution.
    
*   Handling **loops and redundant paths** is crucial for optimization.
