Download Link: https://assignmentchef.com/product/solved-cs688-assignment1-factorization
<br>
Introduction: In this assignment, you will experiment with different aspects of modeling, learning, and applying a Bayesian network to answer probability queries. This assignment focuses on the heart disease diagnosis domain and uses part of a real clinical data set.

Data Set: The data set consists of 9 variables as described below. The number of each variable corresponds to it’s column number in the data set files. There are five sets of training and test data files in standard comma-separated-value (CSV) format. The files are named <em>data-train-i.txt </em>and <em>data-test-i.txt </em>for <em>i </em>from 1 to 5.

<table width="562">

 <tbody>

  <tr>

   <td width="64">Number</td>

   <td width="51">Name</td>

   <td width="163">Description</td>

   <td width="285">Values</td>

  </tr>

  <tr>

   <td width="64">1</td>

   <td width="51">A</td>

   <td width="163">Age</td>

   <td width="285">1:<em>&lt; </em>45, 2: 45 − 55, 3:≥ 55</td>

  </tr>

  <tr>

   <td width="64">2</td>

   <td width="51">G</td>

   <td width="163">Gender</td>

   <td width="285">1:Female, 2:Male;</td>

  </tr>

  <tr>

   <td width="64">3</td>

   <td width="51">CP</td>

   <td width="163">Chest Pain</td>

   <td width="285">1:Typical, 2:Atypical, 3:Non-Anginal, 4:None</td>

  </tr>

  <tr>

   <td width="64">4</td>

   <td width="51">BP</td>

   <td width="163">Blood Pressure</td>

   <td width="285">1:Low, 2:High</td>

  </tr>

  <tr>

   <td width="64">5</td>

   <td width="51">CH</td>

   <td width="163">Cholesterol</td>

   <td width="285">1:Low, 2:High</td>

  </tr>

  <tr>

   <td width="64">6</td>

   <td width="51">ECG</td>

   <td width="163">Electrocardiograph</td>

   <td width="285">1:Normal, 2:Abnormal</td>

  </tr>

  <tr>

   <td width="64">7</td>

   <td width="51">HR</td>

   <td width="163">Exercise Heart Rate</td>

   <td width="285">1:Low, 2:High</td>

  </tr>

  <tr>

   <td width="64">8</td>

   <td width="51">EIA</td>

   <td width="163">Exercise Induced Angina</td>

   <td width="285">1:No, 2:Yes</td>

  </tr>

  <tr>

   <td width="64">9</td>

   <td width="51">HD</td>

   <td width="163">Heart Disease</td>

   <td width="285">1:No, 2:Yes</td>

  </tr>

 </tbody>

</table>

Model: We will consider applying a Bayesian network with the following structure to the data set.

<ol>

 <li>Factorization : Write down the factorization of the Bayesian network joint distribution implied by the structure shown above. (report)</li>

 <li> Likelihood Function: Using the notation for the parameters of CPTs introduced in Lecture</li>

</ol>

4 (ie: <em>P<sub>θ</sub></em>(<em>HD </em>= <em>hd</em>|<em>CH </em>= <em>ch,BP </em>= <em>bp</em>) = <em>θ<sub>hd</sub><sup>HD</sup></em><sub>|<em>ch,bp</em></sub>), write down the log likelihood of the Bayesian network model as a function of the parameters <em>θ </em>given <em>N </em>data cases. (report)

<ol start="3">

 <li> Maximum Likelihood Estimates: Using the notation for the parameters of CPTs introduced in Lecture 4, derive the maximum likelihood estimate for the parameterstarting from the log likelihood function. Show all of your work. (report)</li>

 <li>CPT Data Structures In this question, you will describe and implement conditional probability table data structures for the Bayesian network shown above.

  <ul>

   <li>To implement the network shown above, you will need to choose a data structure to represent conditional probability tables. There are many possible choices including classes of your own design. As your answer to this question, explain what data structure you chose to represent CPTs and how it represents CPTs with different numbers of parents and different variable cardinalities. If you implement a custom class, describe its member variables and methods. If you use an existing data structure (lists, array, dictionary, etc.), describe how. (report)</li>

   <li>(<em>5 pts</em>) In the BayesNet class contained in code/bn.py, implement the __init__ method. This method should create the set of CPTs needed to represent the above model as member variables according to your approach described in 4.1. You should initialize each CPT to the uniform distribution over the target variable for each setting of the parent variables. (code)</li>

   <li>(<em>5 pts</em>) In the BayesNet class contained in code/bn.py, implement the methods get and set. These methods provide basic functions to get the current value of a specific probability from a CPT member variable and to set a specific probability in a CPT member variable in a way that is independent of your CPT implementation. (code)</li>

  </ul></li>

 <li>(<em>15 points</em>) Learning: In this question, you will describe and implement learning for the Bayesian network shown above.

  <ul>

   <li>(<em>5 pts</em>) To implement maximum likelihood learning for a Bayesian network model, the parameters of each CPT must be estimated from data. This can be accomplished by writing unique code for every CPT in the model. This is conceptually simple, but highly redundant and error prone. It is also possible to write a single general function that can estimate the parameters for any CPT. This is conceptually more complex, but provides much more compact code. As your answer to this question, describe your approach to implementing learning. (report)</li>

   <li>(<em>10 pts</em>) In the BayesNet class contained in code/bn.py, implement the fit function according to the approach you described in part 1. The fit function must implement maximum likelihood parameter estimation for all CPTs in the model. (code)</li>

  </ul></li>

 <li>(<em>10 points</em>) Probability Queries: In this question, you will derive and implement solutions to two different probability queries.

  <ul>

   <li>(<em>5 pts</em>) For each of the two queries listed below, show how the query can be expressed in terms of the factorized joint distribution for the Bayesian network. Simplify the expressions wherever possible using the conditional independence properties of the network structure. Show your work. (report)</li>

  </ul></li>

</ol>

<ul>

 <li><em>P</em>(<em>CH</em>|<em>A </em>= 2<em>,G </em>= <em>M,CP </em>= <em>None,BP </em>= <em>L,ECG </em>= <em>Normal,HR </em>= <em>L,EIA </em>= <em>No,HD </em>= <em>No</em>)</li>

 <li><em>P</em>(<em>BP</em>|<em>A </em>= 2<em>,CP </em>= <em>Typical,CH </em>= <em>H,ECG </em>= <em>Normal,HR </em>= <em>H,EIA </em>= <em>Y es,HD </em>= <em>No</em>)</li>

</ul>

6.2. (<em>5 pts</em>) In code/queries.py, implement the methods query_5_a and query_5_b. These two functions take an instance of the BayesNet class as input and should compute the query distributions for queries (a) and (b). (code)

<ol start="7">

 <li>(<em>15 points</em>) Classification: In this question, we will assess the ability of the model to correctly predict the occurrence of heart disease given the values of all of the other variables in the network.

  <ul>

   <li>(<em>5 pts</em>) Write down the probability distribution over the heart disease variable (HD) given the remaining variables for the Bayesian Network model shown above. Simplify the result using the conditional independence properties of the network (report).</li>

   <li>(<em>5 pts</em>) Implement the predict_hd method of the BayesNet class in code/bn.py. This method will predict if a patient has heart disease or not using the probability of heart disease given the remaining variables as derived in 7.1. Your method should predict Yes (2) if the probability of heart disease if greater than 0.5 and should predict No (1) otherwise (code).</li>

   <li>(<em>5 pts</em>) We will follow a standard five-fold cross-validation protocol to assess the performance of classifier derived from the model in 7.2. For each training file <em>i</em>, use your Bayesian network implementation to learn the parameters of the model, then make predictions for the heart disease variable for each data case <em>n </em>in test file <em>i </em>using the predict_hd method. For each test file <em>i</em>, compute the prediction accuracy <em>A<sub>i </sub></em>as the number of cases correctly predicted divided by the total number of cases. Lastly, compute the mean prediction accuracy over the five test files (the average of <em>A</em><sub>1 </sub>to <em>A</em><sub>5</sub>) and the standard deviation of the prediction accuracy over the five test files (the standard deviation of <em>A</em><sub>1 </sub>to <em>A</em><sub>5</sub>). Report the mean and the standard deviation of the prediction accuracy that you find (report). Add your code to accuracy.py (code).</li>

  </ul></li>

 <li>(<em>15 points</em>) Modeling: In this question, you will design, implement and evaluate your own network structure for the heart disease domain.

  <ul>

   <li>(<em>2 pts</em>) Provide a figure showing the graphical model for your network (report).</li>

   <li>(<em>3 pts</em>) Write down the factorization for your network (report).</li>

   <li>(<em>3 pts</em>) Briefly describe some of the choices that went into the design of your network (report).</li>

   <li>(<em>5 pts</em>) Implement your network in code/bn_custom.py. The API for this class is identical to that of code/bn.py. You must support the fit, get, set, and predict_hd methods (code).</li>

   <li>(<em>2 pts</em>) As in the previous question, apply the five-fold cross-validation protocol to assess and report the mean prediction accuracy of your model, along with its standard deviation. (report)</li>

  </ul></li>

</ol>