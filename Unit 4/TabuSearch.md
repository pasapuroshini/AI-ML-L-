### 🔍 **Overview:**

* **Tabu Search** is an iterative search method.

* It explores the solution space of an optimization problem.

* It avoids revisiting already-explored (non-improving) solutions by using a special memory structure called the **tabu list**.

---

### 💡 **Why is Tabu Search Useful?**

* In large search spaces, simple local search techniques (e.g., hill climbing) can get stuck in **local optima**.

* Tabu Search helps escape local optima by:

  * Exploring new areas of the solution space.

  * Blocking moves that would lead to previously visited solutions.

---

### ⚙️ **How Tabu Search Works:**

1. **Step 1:** Start with an initial solution (random or heuristic-based).

2. **Step 2:** Evaluate the neighboring solutions.

3. **Step 3:** Select the best neighboring solution that is *not* in the **tabu list**.

4. **Step 4:** Add the current solution to the tabu list.

5. **Step 5:** Repeat the process until a stopping condition is met (like max iterations or convergence).

---

### 🧭 **Example: Solving TSP using Tabu Search**

* **Problem:** Optimize the route of visiting cities to minimize total distance.

* **Initial Solution:** Random route (e.g., A → B → C → D → E → A).

* **Neighborhood Exploration:** Swap two cities to get new routes, like A → C → B → D → E → A.

* **Move to Best Neighbor:** Choose the one with the **shortest total distance**.

* **Tabu List:** Prevent revisiting routes by storing recent ones in a tabu list (e.g., for 10 iterations).

---

### ✅ Summary

* Tabu Search is great for escaping **local optima**.

* It uses **memory-based constraints (tabu list)** to guide the search process.

* Effective for hard combinatorial problems like **TSP, scheduling, routing**, etc.

* ## 📘 **Tabu Search Algorithm – Full Notes**

  ---

### 🔹 Introduction

  * **Tabu Search** is an **iterative search algorithm** designed for solving **optimization problems**.

  * It is an **improvement over hill climbing** as it avoids getting trapped in local optima by using a **memory structure**.

  ---

### 🔹 Key Concepts

  * **Hill Climbing Limitation:**

    * Tends to get stuck in **local optima**.

    * Cannot backtrack once at a peak (local minimum or maximum).

  * **Tabu Search Advantage:**

    * Uses **memory (tabu list)** to avoid revisiting previously explored bad solutions.

    * Allows **non-improving moves** to explore the search space more broadly.

  ---

### 🔹 How It Works

  1. **Start with an Initial Solution**

     * This could be a **random solution** or generated using some **heuristic**.

  2. **Generate a Set of Neighboring Solutions**

     * Neighborhood is defined based on the problem (e.g., swap cities in TSP).

  3. **Evaluate and Select the Best Neighbor**

     * Even if it's **worse** than the current solution, accept it if it's not in the tabu list.

  4. **Update the Tabu List**

     * Add the **current solution** to the list to avoid revisiting.

     * Maintain a **fixed size** for the tabu list (e.g., last 10 moves).

  5. **Repeat the Process**

     * Continue for a **predefined number of iterations** or until **convergence** is reached.

  ---

### 🔹 Important Terminologies

  * **Tabu List:**

    * A short-term memory that stores a list of **forbidden moves** or recently visited solutions.

    * Prevents cycling back to previous states.

  * **Aspiration Criteria:**

    * Allows overriding the tabu status if a **tabu move results in a better overall solution** than previously found.

  * **Diversification:**

    * Encourages the algorithm to **explore new areas** of the search space.

  * **Intensification:**

    * Focuses the search around the **best solutions found so far**.

  ---

### 🔹 Application: Traveling Salesman Problem (TSP)

  * **TSP Objective:**

    * Visit each city once and return to the starting point while **minimizing total distance**.

  * **Initial Solution Example:**

    * A → B → C → D → E → A

  * **Neighborhood Definition:**

    * Swap two cities to generate new routes.

  * **Iteration Steps:**

    1. Select a random route.

    2. Compute the total distance of each neighboring route.

    3. Choose the best neighbor **not in tabu list**.

    4. Add the current route to the tabu list.

    5. Repeat the process.

  ---

### 🔹 Summary

  * **Tabu Search** is a powerful method for **escaping local optima**.

  * Efficient for solving **combinatorial optimization problems** like:

    * **Traveling Salesman Problem**

    * **Job Scheduling**

    * **Vehicle Routing**

  * Balances **exploration** and **exploitation** using:

    * **Tabu List**

    * **Aspiration Criteria**

    * **Intensification/Diversification strategies**
