# **Week 1: Threshold Logic Units and Boolean Logic Gates**

## **1\. Objective**

The objective of this week's work was to understand how Boolean logic gates can be represented using threshold-based neural units and to explore the limitations of single-layer perceptrons when implementing non-linearly separable functions.

The work focused on implementing basic Boolean gates using NumPy, examining their decision boundaries, and constructing a Multi-Layer Perceptron (MLP) to implement the XOR gate.

## **2\. Theoretical Background**

### 2.1 Threshold Logic Unit (TLU)

A Threshold Logic Unit computes a weighted sum of its inputs, adds a bias, and applies a step activation function to produce a binary output.

For two inputs, the weighted sum is:

$z=\ \sum\limits_{i\ =\ 1}^{n}{w}_{i}{x}_{i}+\ b$

The binary step activation is defined as:

$f(z)\ =\ Step(z)$  
Where:

* Output \= 1 when z \>= 0  
* Output \= 0 when z \< 0

Here, ${x}_{1}$ and ${x}_{2}$ are the inputs, ${w}_{1}$ and ${w}_{2}$ are their weights, and $b$ is the bias. The weights and bias determine the decision boundary and the output produced for each input combination.

### 2.2 Boolean Logic Gates

AND, OR, and NAND can be implemented using a single threshold logic unit by selecting appropriate weights and biases.

For this implementation, the following parameters were used:

| GATE | W1 | W2 | Bias(b) | Decision rule |
| :---: | :---: | :---: | :---: | :---: |
| AND | 1 | 1 | \-1.5 | $x1+x2>=1.5$ |
| OR | 1 | 1 | \-0.5 | $x1\ +x2\ >=0.5$ |
| NAND | \-1 | \-1 | 1.5 | $x1+x2<\ 1.5$ |

The NAND implementation uses negative weights, reversing the direction of the threshold decision relative to the corresponding AND gate.

### 2.3 Linear Separability and XOR

A Boolean function is linearly separable if its output classes can be separated by a single linear decision boundary.

AND, OR, and NAND are linearly separable. XOR is not linearly separable because its positive outputs occur at opposite corners of the binary input space.

The XOR truth table is:

| ${x}_{1}$ | ${x}_{2}$ | XOR Output |
| :---- | :---- | :---- |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

No single linear threshold boundary can separate the two output classes correctly for all four combinations. This motivates the use of a multilayer architecture.

## **3\. Implementation Methodology**

### 3.1 NumPy-Based TLU

The TLU was implemented in Python using NumPy. The implementation computes the dot product of the input vector and the weight vector, adds the bias, and applies the step activation function.

The same TLU function was reused to implement AND, OR, and NAND by changing their weights and biases.

The four binary input combinations were tested for each gate to compare the predicted outputs against the expected truth table.

### 3.2 Decision Boundary Visualization

Scatter plots were generated to visualize the binary input points and their corresponding gate outputs. Decision boundaries were plotted to illustrate how the selected weights and biases divide the input space into different output regions.

These visualizations support the mathematical explanation of each threshold gate. The truth-table checks provide the direct verification of gate correctness for the binary inputs.

### 3.3 XOR Using a Multi-Layer Perceptron

To implement XOR, an MLP architecture with one hidden layer containing two neurons was constructed using the previously defined TLU function.

The architecture is:

* **Hidden neuron 1:** Implements OR.  
* **Hidden neuron 2:** Implements NAND.  
* **Output neuron:** Implements AND over the two hidden outputs.

The two hidden neurons receive the same inputs in parallel. Their outputs are then passed to the final AND neuron.

The resulting Boolean expression is:

$XOR({x}_{1},{x}_{2})=\ AND(OR({x}_{1},{x}_{2}),NAND({x}_{1},{x}_{2}))$

This works because OR is true when at least one input is true, while NAND is true unless both inputs are true. Their conjunction is therefore true exactly when one input is true.

The MLP was evaluated on all four binary input combinations. Its predictions matched the XOR truth table.

### 3.4 XOR Output-Region Visualization

To visualize the constructed network's behavior, predictions were computed over a dense grid of continuous-valued input pairs. These predictions were used to create a contour plot showing the network's output regions.

The grid visualization illustrates the regions induced by the network's threshold operations. It is not evidence of training or generalization on a continuous dataset. Correct XOR behavior was verified separately using the four binary input combinations.

### 3.5 Bipolar Representation of Logic Gates

The implementation also explored a bipolar representation in which the activation function returns either (-1) or (+1):

$z=\ \sum\limits_{i\ =\ 1}^{n}{w}_{i}{x}_{i}+\ b$  
$f(z)\ =\ sign(z)$  
Where:

* Output \= 1 when z \>= 0  
* Output \= \-1 when z \< 0

The bipolar inputs were evaluated using the combinations ((-1,-1)), ((-1,+1)), ((+1,-1)), and ((+1,+1)).

Weights and biases were selected to implement AND, OR, and NAND under this bipolar convention. The resulting outputs were visualized to illustrate the corresponding threshold regions.

The bipolar representation uses a different input and output encoding from the binary (0/1) implementation. The weights, biases, and activation convention must therefore be interpreted together.

## **4\. Results and Observations**

The following observations were made during the implementation:

1. AND, OR, and NAND were represented using threshold logic units with manually selected weights and biases.  
2. The corresponding binary truth-table outputs matched the expected Boolean gate behavior.  
3. The XOR gate could not be represented by a single linear threshold unit because its output classes are not linearly separable.  
4. An MLP combining OR and NAND hidden neurons with an AND output neuron correctly implemented XOR for all four binary input combinations.  
5. Decision-boundary and output-region plots provided visual explanations of the threshold operations.  
6. The bipolar implementation demonstrated an alternative (-1/+1) encoding for Boolean logic gates.

The work established a basic implementation framework for exploring Boolean functions through threshold-based neural architectures.

## **5\. Limitations**

This week's implementation primarily focused on mathematical foundations, manually selected gate parameters, and functional verification.

The XOR MLP was constructed from known logic-gate operations rather than trained from a dataset. The continuous-grid plot was used for visualization, not as a continuous-data training or generalization experiment.

No FPGA deployment, hardware synthesis, hardware resource measurements, latency benchmarks, or power-consumption measurements were established by this week's work.

These limitations define the scope of the current implementation and provide context for evaluating any subsequent experiments.

## **6\. Relevance to Edge AI**

Threshold logic units and Boolean logic gates provide a useful foundation for investigating the relationship between neural computation and digital logic.

The implementations in this week demonstrate how simple Boolean operations can be expressed through weighted sums, thresholds, and small neural architectures. This provides a conceptual starting point for exploring more complex Boolean neural networks and potential hardware-oriented implementations.

However, hardware efficiency and practical Edge AI performance would require additional implementation and measurement beyond the experiments documented here.

## **7\. Files and Reproducibility**

The Python implementation and visualizations are provided in the accompanying notebook:

* `[01\_tlu\_logic\_gates.ipynb](https://colab.research.google.com/drive/1AD5X1YMD7OfPgNsFbxnuneJHtB-Oz8xw?usp=sharing)`

The notebook contains the TLU function, Boolean gate implementations, XOR MLP, binary input tests, and visualizations.

## **8\. Summary**

Week 1 established the foundational concepts and implementations for representing Boolean logic using threshold logic units and multilayer neural architectures. The key result was the correct construction of XOR from OR, NAND, and AND operations, demonstrating how a multilayer architecture can represent a Boolean function that a single linear threshold unit cannot implement.

These foundations can support further exploration of neural network implementations, optimization approaches, and potential hardware-oriented extensions in subsequent work.

