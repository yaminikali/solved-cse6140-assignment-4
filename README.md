Download Link: https://assignmentchef.com/product/solved-cse6140-assignment-4
<br>



<h1>1             Branch and Bound &amp; Local Search</h1>

<ol>

 <li>Devise a branch-and-bound algorithm for the Minimum SET COVER problem. Thisentails deciding:

  <ul>

   <li>What is a subproblem?</li>

   <li>How do you choose a subproblem to expand?</li>

   <li>How do you expand a subproblem?</li>

   <li>What is an appropriate lowerbound?</li>

  </ul></li>

</ol>

Do you think that your choices above will work well on typical instances of the problem? Why?

<ol start="2">

 <li>Outline a simple greedy heuristic for the SET COVER problem, and explain why itfinds a valid solution and its running time.</li>

 <li>Imagine you wanted to use a local search method to solve Minimum SET COVER suchas Simulated Annealing or Iterated Local Search. Imagine a candidate solution is a subset of the sets that might or might not cover all elements in the Universe set U.

  <ul>

   <li>What could be a possible scoring function for such candidate solutions?</li>

   <li>What would be a Neighborhood (or Moves) you would consider using for your local search to move from one candidate solution to other ’nearby’ solutions? How many potential neighbors can a candidate solution have under your Neighborhood (using Big-Oh)?</li>

   <li>Why would you consider adding Tabu Memory and what would be remembered in your Tabu Memory?</li>

  </ul></li>

</ol>

<h1>2             Approximation using Greedy Heuristics</h1>

Suppose you are in charge of unloading containers from ships arriving at a port onto trucks. A ship arrives with <em>n </em>containers of weight <em>w</em><sub>1</sub><em>,w</em><sub>2</sub><em>,…,w<sub>n </sub></em>tons. Standing on the dock is a set of trucks, each of which can hold 1 ton of weight. (You can assume that none of the containers weighs more than 1 ton, since in this case you would not be able to transport it.) You can stack multiple containers in each truck subject to the weight restriction of 1 ton. Hoping to minimize your truck rental expenses, you aim to minimize the number of trucks needed in order to carry all the containers.

You start with the following greedy strategy. Start with an empty truck and begin loading containers 1<em>,</em>2<em>,</em>3<em>,… </em>onto it until you get to a container that would overflow the weight limit. Now, declare this truck “loaded” and send it off; then continue the process with a fresh truck.

After trying (and failing) to prove that this greedy algorithm is optimal, you decide to attempt to come up with a counter-example to see if you can discover that your strategy is <strong>not </strong>optimal.

<ul>

 <li>Provide an example of a set of weights and a value of <em>K </em>for which your algorithm does <em>not </em>use the minimum possible number of trucks. State the number of trucks used by the algorithm for this example, and the true minimum number of trucks needed.</li>

</ul>

You realize sadly that your problem is in fact NP-complete. However, this renews your faith in your greedy strategy. You try to come up with an approximation ratio.

<ul>

 <li>Let be the total weight of all <em>n </em> Let <em>t</em><sup>∗ </sup>be the minimum number of trucks you need to rent to transport the <em>n </em>containers. Provide a lower bound for <em>t</em><sup>∗</sup>, and argue in support of your bound.</li>

 <li>Suppose your greedy solution uses an even number of trucks, <em>t </em>= 2<em>z </em>where <em>z </em>is a positive integer. You consider these 2<em>z </em>trucks in consecutive pairs. What is a lower bound for the weight of containers in each consecutive pair? Argue in support of your bound.</li>

 <li>Using (b) and (c), prove an approximation ratio of 2 for your algorithm.</li>

 <li>Prove the same approximation ratio for the case when your greedy approach uses anodd number of trucks, <em>t </em>= 2<em>z </em>+ 1.</li>

</ul>

You realize that you might be sending away trucks that still have room for containers that will be unloaded later on. Hoping to improve your strategy, you decide not to dispatch trucks as they are filled, but to keep them around until all <em>n </em>containers have been loaded. Then, you employ the following greedy strategy. Starting with the first truck, see if the container will fit without overloading it. If so, place the container into the first truck; otherwise, consider each subsequent truck in turn and place the container in the first truck that can accommodate it.

<ul>

 <li>Argue that this approach leaves at most one truck less than half full.</li>

 <li>Show that the number of trucks you would use with the second strategy is never morethan d2<em>W</em></li>

 <li>Prove an approximation ratio of 2 for this strategy.</li>

</ul>

<h1>3             Modeling with ILP</h1>

Formulate the following problems as integer linear programs. In each case, state how many constraints and variables you used.

<ul>

 <li>The independent set problem: Given an undirected graph <em>G </em>= (<em>V </em>;<em>E</em>), find a maximum independent set, that is, a maximum subset of vertices in which no two vertices are adjacent.</li>

 <li>The facility location problem: We are given <em>n </em>potential facility locations and a list of <em>m </em>clients who need to be serviced from these locations. There is a fixed cost <em>f<sub>j </sub></em>of opening a facility at location <em>j</em>, while there is a cost <em>c<sub>ij </sub></em>of serving client <em>i </em>from facility <em>j</em>. The goal is to select a set of facility locations and assign each client to one facility, while minimizing the total cost.</li>

 <li>The Sudoku problem: Given is an <em>n</em><sup>2 </sup>× <em>n</em><sup>2 </sup>matrix (for some positive integer <em>n</em>), which contains some matrix entries pre-filled with integral values between 1 and <em>n</em><sup>2</sup>. The task is to fill the remaining entries with integers from {1<em>,</em>2<em>,…,n</em><sup>2</sup>}, such that each row, each column, and each of the <em>n</em><sup>2 </sup>major <em>n </em>× <em>n </em>submatrices contains each integer 1 through <em>n</em><sup>2 </sup>exactly once.</li>

</ul>