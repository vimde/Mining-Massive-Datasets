## Analysis of Large Graphs
* Web can be represented as a directed graph with web pages as nodes and hyperlinks as edges.
* In order to determine the importance of web pages, we can rank the nodes.
* The idea is that some pages will have lots of edges pointing to it. So they may have high importance.

#### Link Analysis Algorithms (approaches to compute importance of nodes in a graph)
* Page Rank
* Hubs and Authorities (HITS)
* Topic-Specific (Personalized) Page Rank
* Web Spam Detection Algorithms

## PageRank: The Flow Formulation
* Links are treated as votes. Page is more important if it has more links.
* Two types of links
    * In-links
    * Out-links
* All in-links are not equal. Links from important pages have more weight and it is a recursive process to compute the importance.
* Importance of a page depends on the importance of other pages pointing to it.

#### Recursive formulation
* Each link is considered a vote and its importance is proportional to the importance of source web page
* If page j with importance rj has n out-links, each link gets rj/n votes
* Page j's own importance = sum of the votes of its in-links
* A page is important if it's pointed to by other important pages

Formula:
![Formula](https://github.com/vimde/Mining-Massive-Datasets/blob/master/Module%202-%20PageRank/Images/Formula.PNG)
   
Example:
![Example](https://github.com/vimde/Mining-Massive-Datasets/blob/master/Module%202-%20PageRank/Images/Example.PNG)

* 3 equations, 3 unknowns and no constants. There could be infinite solutions to this sort of equations.
* An additional constraint forces it to be unique

Solution:
![Solution](https://github.com/vimde/Mining-Massive-Datasets/blob/master/Module%202-%20PageRank/Images/Solution.PNG)

* We can use any Linear System equation solving method such as Gaussian Elimination but it works well for small graphs and not for huge ones
* So we need a different formulation
