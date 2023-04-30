Download Link: https://assignmentchef.com/product/solved-ics2205-assignment-1
<br>
<h1>     Background</h1>

Nowadays, one can find various data sets that have been released to the public with the purpose of allowing people to discover and visualise interesting nuggets of information from these datasets.

For example, on 31st August 2015, the US State Department released a considerable number of emails that were the source of controversy for Hillary Clinton since she was using a non-government email server when she was secretary of state. One can download such emails from <a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a>. Moreover, one may also find various demos that visualise interesting knowledge nuggets extracted from this dataset<a href="#_ftn2" name="_ftnref2"><sup>[2]</sup></a>.

As a further example of data visualisation, one may refer to the site MovieGalaxies<a href="#_ftn3" name="_ftnref3"><sup>[3]</sup></a> that provides insight into the world of movies by displaying the interactions between the actors participating in that movie, as a network. The visualisation used, distinguishes between the various actors and the importance of their roles within a movie, by displaying nodes with different colours and sizes. Furthermore, various metrics are computed, such as the betweenness centrality and degree for each node, and the clustering coefficient, diameter and path length for the whole network.

<h1>2           Specifications</h1>

This project consists of <strong>TWO </strong>tasks, with each task being assigned 50% of the mark for this project. You are to address <strong>BOTH </strong>tasks. The dataset that you will use is the Enron dataset<a href="#_ftn4" name="_ftnref4"><sup>[4]</sup></a>. We have however filtered the dataset that now contains over 279K emails. It contains emails from about 150 users, mostly senior management of Enron, organised into folders. This dataset is being made available to you on Google drive<a href="#_ftn5" name="_ftnref5"><sup>[5]</sup></a>. In the following sections we provide the details for each of the two tasks.

<h2>2.1         Task 1: Text Analysis</h2>

For this deliverable, you are expected to perform text analysis over the dataset and to create a Web-based dashboard to visualise the results.

<ol>

 <li>install a Web server on your machine to host your Web-based dash-board;</li>

 <li>implement an interactive dashboard that allows the user to view akeyword cloud. It is recommended to use a library such as D3<a href="#_ftn6" name="_ftnref6"><sup>[6]</sup></a> embedded within HTML, CSS for styling and JavaScript for additional dynamic functionality. However, you could also use other existing libraries. Provide a visualisation of a single level of clustering of the users. When clicking upon a cluster, the keyword cloud associated with that cluster should be visualised; iii. To perform the text analysis you need to:

  <ol>

   <li>Extract the text from each email;</li>

   <li>Perform lexical analyses to extract the separate words, and tofold them all to lower case;</li>

   <li>Use a standard stop-word list for English to filter out the stopwords;</li>

   <li>Use an implementation of Porter’s stemmer to reduce terms totheir stems (note that you may find a ready-made implementation provided that you reference its source);</li>

   <li>Calculate term weights using TF.IDF. All emails between any 2distinct senders/recipients should be considered as a single document. In this way, the important words that characterise a particular interaction will be given high weights;</li>

   <li>Represent each correspondent as a vector of features. Each termweight for the correspondent vector should be the average weight of that term across all documents in which the correspondent participated (as sender or receiver);</li>

   <li>Use the highest-weighted <em>n% </em>of the terms for each correspondent to build the correspondent keyword-cloud. This keyword-cloud will show what concepts the correspondent generally talks about. <em>n </em>can be determined arbitrarily so that the keyword-cloud does not contain neither too much nor too few words;</li>

   <li>Use the correspondent vectors to cluster the users using the <em>kmeans </em> The choice of <em>k </em>is up to you. Note that you only need to do a <strong>single </strong>level of clustering, that is, no hierarchies are being requested. The clusters need to be visualised using an interactive bubble chart (or equivalent), and when a cluster bubble is clicked, the keyword-cloud representing that cluster should be displayed.</li>

   <li>You need to write a short report with a <strong>maximum length of 4 pages </strong>that clearly describes the work done, including aspects related to design and implementation, as well as the use of any third party libraries/tools.</li>

  </ol></li>

</ol>

<strong>NOTE</strong>: You can use NLTK or other ready made tools to handle parts a) to d). However, you are expected to implement your own <em>TF.IDF </em>weighting scheme, <em>Cosine Similarity </em>measure and <em>k-means </em>clustering.

This part of the project is being allocated <strong>50 marks</strong>.

<h2>2.2         Task 2: Graph Analysis</h2>

This component focuses on the analysis and visualisation of the email corpus as a graph where the nodes represent the correspondents (senders/recipients) and each edge represents the correspondence between any TWO correspondents.

You are expected to:

<ol>

 <li>transform the provided dataset into a suitable format for analysis andvisualisation. You can use NetworkX or some other library to create the graph;</li>

 <li>create a Jupyter Notebook and analyse the graph by computing thefollowing:

  <ul>

   <li><em>Degree distribution</em>: generate i) the undirected distribution of the graph <em>G<sub>u</sub></em>, ii) the in-degree distribution <em>G<sub>i </sub></em>and iii) the out-degree distribution <em>G<sub>o</sub></em>. <strong>Create </strong>plots for these distributions.</li>

  </ul></li>

</ol>

The degree distribution <em>P</em>(<em>k</em>) measures the probability that a randomly chosen node has degree <em>k</em>. For a graph <em>G </em>the degree distribution can be summarized using a normalized histogram. This means that the histogram is normalized by the total number of nodes. To compute the degree distribution of a graph use

, whereby <em>N<sub>k </sub></em>is the number of nodes with degree <em>k </em>and <em>N </em>is the number of nodes. Think of this distribution as the probability that a randomly chosen node has degree <em>k</em>;

<ul>

 <li><em>Diameter</em>: <em>D </em>the longest shortest path between any two nodes in the network;</li>

 <li><em>Average path length</em>: <em>P<sub>avg </sub></em>this is the average length of the shortest paths between the nodes in the graph;</li>

 <li><em>Global Clustering coefficient</em>: the clustering coefficient <em>c<sub>c </sub></em>is ratio of the number of connections between the neighbours of each node and the total number of possible connections between the same neighbours. The global clustering coefficient <em>C<sub>c </sub></em>is the mean over all the individual <em>c<sub>c</sub></em>;</li>

 <li><em>Compactness</em>: compactness is the ratio between the number of existing edges and the number of all the possible edges , where <em>E </em>is the total number of edges and N is the total number of vertices in the graph. Compactness can have a value between 0 and 1;</li>

 <li><em>Betweenness centrality</em>: considers those nodes which are traversed in many shortest paths to be more important than others;</li>

 <li><em>PageRank</em>: returns a ranking over the influential nodes in the network that extends beyond their direct connections. iii. provide a visualisation of the graph that has the following features: (a) The correspondents’ activity: the node size should be proportional to the number of emails sent/received by the corresponding sender/recipient. In this way, one can immediately recognise the most active correspondents;</li>

</ul>

(b) The level of interaction between any 2 correspondents: the edge width should be indicative of the number of emails passed between the correspondents represented by the surrounding edges.

<ol>

 <li>in the Jupyter notebook you need to clearly elaborate (as markdown) how you performed the analysis and discuss the findings from the distribution plots and the significance of the results of the various metrics (for instance compare compactness and the global clustering coefficient, and betweenness and PageRank).</li>

</ol>

For this task, <strong>50 marks </strong>are being allocated.

<a href="#_ftnref1" name="_ftn1">[1]</a> <a href="https://www.kaggle.com/c/hillary-clinton-emails/data">https://www.kaggle.com/c/hillary-clinton-emails/data</a>

<a href="#_ftnref2" name="_ftn2">[2]</a> <a href="https://www.kaggle.com/c/hillary-clinton-emails/scripts">https://www.kaggle.com/c/hillary-clinton-emails/scripts</a>

<a href="#_ftnref3" name="_ftn3">[3]</a> <a href="http://moviegalaxies.com/">http://moviegalaxies.com/</a>

<a href="#_ftnref4" name="_ftn4">[4]</a> <a href="https://www.cs.cmu.edu/~./enron/">https://www.cs.cmu.edu/</a><a href="https://www.cs.cmu.edu/~./enron/">~</a><a href="https://www.cs.cmu.edu/~./enron/">./enron/</a>

<a href="#_ftnref5" name="_ftn5">[5]</a> <a href="https://drive.google.com/file/d/1vqFyzWBHLtMR5SBXTl67hEaN2MLoV79b/view?usp=sharing">https://drive.google.com/file/d/1vqFyzWBHLtMR5SBXTl67hEaN2MLoV79b/view?</a>

<a href="https://drive.google.com/file/d/1vqFyzWBHLtMR5SBXTl67hEaN2MLoV79b/view?usp=sharing">usp=sharing</a>

<a href="#_ftnref6" name="_ftn6">[6]</a> <a href="https://d3js.org/">https://d3js.org</a>