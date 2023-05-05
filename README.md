Download Link: https://assignmentchef.com/product/solved-ece232ee-project-2-social-network-mining
<br>
In this project, we will study the various properties of social networks. In the first part of the project, we will study an undirected social network (Facebook). In the second part of the project, we will study a directed social network (Google +).

<h1>1      Facebook network</h1>

In this project, we will be using the dataset given below: <a href="http://snap.stanford.edu/data/egonets-Facebook.html">http://snap.stanford.edu/data/egonets-Facebook.html</a>

The Facebook network can be created from the edgelist file (<strong>facebook combined.txt</strong>)

<h2>1.1     Structural properties of the facebook network</h2>

Having created the facebook network, we will study some of the structural properties of the network. To be specific, we will study

<ul>

 <li>Connectivity</li>

 <li>Degree distribution</li>

</ul>

Question 1: Is the facebook network connected? If not, find the giant connected component (GCC) of the network and report the size of the GCC.

Question 2: Find the diameter of the network. If the network is not connected, then find the diameter of the GCC.

Question 3: Plot the degree distribution of the facebook network and report the average degree.

Question 4: Plot the degree distribution of question 3 in a log-log scale.

Try to fit a line to the plot and estimate the slope of the line.

<h2>1.2     Personalized network</h2>

A personalized network of an user <em>v<sub>i </sub></em>is defined as the subgraph induced by <em>v<sub>i </sub></em>and it’s neighbors. In this part, we will study some of the structural properties of the personalized network of the user whose graph node ID is 1 (node ID in edgelist is 0). From this point onwards, whenever we are refering to a node ID we mean the graph node ID which is 1 + node ID in edgelist.

Question 5: Create a personalized network of the user whose ID is 1. How many nodes and edges does this personalized network have?

Question 6: What is the diameter of the personalized network? Please state a trivial upper and lower bound for the diameter of the personalized network.

Question 7: In the context of the personalized network, what is the meaning of the diameter of the personalized network to be equal to the upper bound you derived in question 6. What is the meaning of the diameter of the personalized network to be equal to the lower bound you derived in question 6?

<h2>1.3     Core node’s personalized network</h2>

A core node is defined as the nodes that have more than 200 neighbors. For visualization purpose, we have displayed the personalized network of a core node below.

An example of a personal network. The core node is shown in black.

In this part, we will study various properties of the personalized network of the core nodes.

Question 8: How many core nodes are there in the Facebook network.

What is the average degree of the core nodes?

<h3>1.3.1    Community structure of core node’s personalized network</h3>

In this part, we study the community structure of the core node’s personalized network. To be specific, we will study the community structure of the personalized network of the following core nodes:

<ul>

 <li>Node ID 1</li>

 <li>Node ID 108</li>

 <li>Node ID 349</li>

 <li>Node ID 484</li>

 <li>Node ID 1087</li>

</ul>

Question 9: For each of the above core node’s personalized network, find the community structure using Fast-Greedy, Edge-Betweenness, and Infomap community detection algorithms. Compare the modularity scores of the algorithms. For visualization purpose, display the community structure of the core node’s personalized networks using colors. Nodes belonging to the same community should have the same color and nodes belonging to different communities should have different color. In this question, you should have 15 plots in total.

<h3>1.3.2    Community structure with the core node removed</h3>

In this part, we will explore the effect on the community structure of a core node’s personalized network when the core node itself is removed from the personalized network.

Question 10: For each of the core node’s personalized network(use same core nodes as question 9), remove the core node from the personalized network and find the community structure of the modified personalized network. Use the same community detection algorithm as question 9.

Compare the modularity score of the community structure of the modified personalized network with the modularity score of the community structure of the personalized network of question 9. For visualization purpose, display the community structure of the modified personalized network using colors. In this question, you should have 15 plots in total.

<h3>1.3.3    Characteristic of nodes in the personalized network</h3>

In this part, we will explore characteristics of nodes in the personalized network using two measures. These two measures are stated and defined below:

<ul>

 <li><strong>Embeddedness </strong>of a node is defined as the number of mutual friends a node shares with the core node.</li>

 <li><strong>Dispersion </strong>of a node is defined as the sum of distances between every pair of the mutual friends the node shares with the core node. The distances should be calculated in a modified graph where the node (whose dispersion is being computed) and the core node are removed.</li>

</ul>

For further details on the above characteristics, you can read the paper below: <a href="https://arxiv.org/abs/1310.6753">http://arxiv.org/abs/1310.6753</a>

Question 11: Write an expression relating the <strong>Embeddedness </strong>of a node to it’s degree.

Question 12: For each of the core node’s personalized network (use the same core nodes as question 9), plot the distribution of embeddedness and dispersion. In this question, you will have 10 plots.

Question 13:      For each of the core node’s personalized network, plot the community structure of the personalized network using colors and highlight the node with maximum dispersion. Also, highlight the edges incident to this node. To detect the community structure, use FastGreedy algorithm. In this question, you will have 5 plots.

Question 14: Repeat question 13, but now highlight the node with maximum embeddedness and the node with maximum. Also,

highlight the edges incident to these nodes

Question 15: Use the plots from questions 13 and 14 to explain the characteristics of a node revealed by each of this measure.

<h2>1.4     Friend recommendation in personalized networks</h2>

In many social networks, it is desirable to predict future links between pairs of nodes in the network. In the context of this Facebook network it is equivalent to recommending friends to users. In this part of the project, we will explore some neighborhood-based measures for friend recommendation. The network that we will be using for this part is the personalized network of node with ID 415.

<h3>1.4.1    Neighborhood based measure</h3>

In this project, we will be exploring three different neighborhood-based measures. Before we define these measures, let’s introduce some notation:

<ul>

 <li><em>S<sub>i </sub></em>is the neighbor set of node <em>i </em>in the network</li>

 <li><em>S<sub>j </sub></em>is the neighbor set of node <em>j </em>in the network</li>

</ul>

Then, with the above notation we define the three measures below:

<ul>

 <li>Common neighbor measure between node <em>i </em>and node <em>j </em>is defined as</li>

</ul>

<em>CommonNeighbors</em>(<em>i,j</em>) = |<em>S<sub>i </sub></em>∩ <em>S<sub>j</sub></em>|

<ul>

 <li>Jaccard measure between node <em>i </em>and node <em>j </em>is defined as</li>

 <li>Adamic-Adar measure between node <em>i </em>and node <em>j </em>is defined as</li>

</ul>

<h3>1.4.2    Friend recommendation using neighborhood based measures</h3>

We can use the neighborhood based measures defined in the previous section to recommend new friends to users in the network. Suppose we want to recommend <em>t </em>new friends to some user <em>i </em>in the network using Jaccard measure. We follow the steps listed below:

<ol>

 <li>For each node in the network that is not a neighbor of <em>i</em>, compute the jaccard measure between the node <em>i </em>and the node not in the neighborhood of <em>i</em></li>

</ol>

Compute

<ol start="2">

 <li>Then pick <em>t </em>nodes that have the highest jaccard measure with node <em>i </em>and recommend these nodes as friends to node <em>i</em></li>

</ol>

<h3>1.4.3    Creating the list of users</h3>

Having defined the friend recommendation procedure, we can now apply it to the personalized network of node ID 415. Before we apply the algorithm, we need to create the list of users who we want to recommend new friends to. We create this list by picking all nodes with degree 24. We will denote this list as <em>N<sub>r</sub></em>.

Question 16: What is |<em>N<sub>r</sub></em>|?

<h3>1.4.4    Average accuracy of friend recommendation algorithm</h3>

In this part, we will apply the 3 different types of friend recommendation algorithms to recommend friends to the users in the list <em>N<sub>r</sub></em>. We will define an average accuracy measure to compare the performances of the friend recommendation algorithms.

Suppose we want to compute the average accuracy of the friend recommendation algorithm. This task is completed in two steps:

<ol>

 <li>Compute the average accuracy for each user in the list <em>N<sub>r</sub></em></li>

 <li>Compute the average accuracy of the algorithm by averaging across the accuracies of the users in the list <em>N<sub>r</sub></em></li>

</ol>

Let’s describe the procedure for accomplishing the step 1 of the task. Suppose we want to compute the average accuracy for user <em>i </em>in the list <em>N<sub>r</sub></em>. We can compute it by iterating over the following steps 10 times and then taking the average:

<ol>

 <li>Remove each edge of node <em>i </em>at random with probability 0.25. In this context, it is equivalent to deleting some friends of node <em>i</em>. Let’s denote the list of friends deleted as <em>R<sub>i</sub></em></li>

 <li>Use one of the three neighborhood based measures to recommend |<em>R<sub>i</sub></em>| new friends to the user <em>i</em>. Let’s denote the list of friends recommended as <em>P<sub>i</sub></em></li>

 <li>The accuracy for the user <em>i </em>for this iteration is given by</li>

</ol>

By iterating over the above steps for 10 times and then taking the average gives us the average accuracy of user <em>i</em>. In this manner, we compute the average accuracy for each user in the list <em>N<sub>r</sub></em>. Once we have computed them, then we can take the mean of the average accuracies of the users in the list <em>N<sub>r</sub></em>. The mean value will be the average accuracy of the friend recommendation algorithm.

Question 17: Compute the average accuracy of the friend recommendation algorithm that uses:

<ul>

 <li>Common Neighbors measure</li>

 <li>Jaccard measure</li>

 <li>Adamic Adar measure</li>

</ul>

Based on the average accuracy values, which friend recommendation algorithm is the best?

<h1>2      Google+ network</h1>

In this part, we will explore the structure of the Google+ network. The dataset for creating the network can be found in the link below: <a href="http://snap.stanford.edu/data/egonets-Gplus.html">http://snap.stanford.edu/data/egonets-Gplus.html</a>

Create directed personal networks for users who have more than 2 circles. The data required to create such personal networks can be found in the file named <strong>gplus.tar.gz</strong>.

Question 18: How many personal networks are there?

Question 19: For the 3 personal networks (node ID given below), plot the in-degree and out-degree distribution of these personal networks.

Do the personal networks have a similar in and out degree distribution. In this question, you should have 6 plots.

<ul>

 <li>109327480479767108490</li>

 <li>115625564993990145546</li>

 <li>101373961279443806744</li>

</ul>

<h2>2.1     Community structure of personal networks</h2>

In this part of the project, we will explore the community structure of the personal networks that we created and explore the connections between communities and user circles.

Question 20: For the 3 personal networks picked in question 19, extract the community structure of each personal network using Walktrap community detection algorithm. Report the modularity scores and plot the communities using colors. Are the modularity scores similar? In this question, you should have 3 plots.

Having found the communities, now we will explore the relationship between circles and communities. In order to explore the relationship, we define two measures:

<ul>

 <li>Homogeneity</li>

 <li>Completeness</li>

</ul>

Before, we state the expression for homogeneity and completeness, let’s introduce some notation:

<ul>

 <li><em>C </em>is the set of circles, <em>C </em>= {<em>C</em><sub>1</sub><em>,C</em><sub>2</sub><em>,C</em><sub>3</sub><em>,</em>··}</li>

 <li><em>K </em>is the set of communities, <em>K </em>= {<em>K</em><sub>1</sub><em>,K</em><sub>2</sub><em>,K</em><sub>3</sub><em>,</em>··}</li>

 <li><em>a<sub>i </sub></em>is the number of people in circle <em>C<sub>i</sub></em></li>

 <li><em>b<sub>i </sub></em>is the number of people in community <em>K<sub>i </sub></em>with circle information</li>

 <li><em>N </em>is the total number of people with circle information</li>

 <li><em>C<sub>ji </sub></em>is the number of people belonging to community <em>j </em>and circle <em>i</em></li>

</ul>

Then, with the above notation, we have the following expressions for the entropy

(1)

(2)

and conditional entropy

(3)

(4)

Now we can state the expression for homogeneity, <em>h </em>as

(5)

and the expression for completeness, <em>c </em>as

(6)

Question 21: Based on the expression for <em>h </em>and <em>c</em>, explain the meaning of homogeneity and completeness in words.

Question 22: Compute the <em>h </em>and <em>c </em>values for the community structures of the 3 personal network (same nodes as question 19). Interpret the values and provide a detailed explanation.