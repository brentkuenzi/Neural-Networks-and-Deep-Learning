# Chapter 1
## Using neural nets to recognize handwritten digits
### Neural networks vs. human brain
Neural nets use training examples to automatically infer rules for recognizing handwritten digits. This requires large numbers of examples to increase accuracy. Human brains are more like a model pretuned to process images and patterns.

### Perceptrons
- Type of artificial neuron
- Not as commonly used as compared to sigmoid neurons

A perceptron takes several binary inputs, $x_1, x_2, \ldots$ and produces a single binary output:

![alt text](http://neuralnetworksanddeeplearning.com/images/tikz0.png)

So in this example, the perceptron has 3 inputs $x_1, x_2, x_3$. The importance of these inputs to the corresponding output are denoted as weights $w_1,w_2,\ldots$ which are real numbers. The neuron then outputs 0 or 1 which is determined by whether the weighted sum $\sum_j w_j x_j$ is less than or greater than some threshold value. Algebraically:

$\begin{eqnarray}
  \mbox{output} = \left\{ \begin{array}{ll}
      0 & \mbox{if } \sum_j w_j x_j \leq \mbox{ threshold} \\
      1 & \mbox{if } \sum_j w_j x_j > \mbox{ threshold}
      \end{array} \right\.
\tag{1}\end{eqnarray}$

So essentially a perceptron makes decisions by weighing the *evidence*.

Perceptrons can become more complex with multiple layers:

![img](http://neuralnetworksanddeeplearning.com/images/tikz1.png)

where the first layer makes 3 simple decisions by weighing input evidence and the second layer makes decisions by weighing up the results form the first layer of decisions. Even though it looks like these perceptrons have multiple outputs, they dont. They still have a single output but this output is being used as input to multiple perceptrons.

### Simplifying perceptrons
We can simplify the perceptron described above by doing two things:
1) Rewrite the weighted sum equation above as the dot product w $\cdot x \equiv \sum_j w_j x_j$ where *w* and *x* are vectors whose components are the weights and inputs, respectively.
2) Move the threshold to the other side of the inequality and replace it with the perceptron bias $b \equiv
-\mbox{threshold}$

Thus we rewrite our perceptron rule:
$\begin{eqnarray}
  \mbox{output} = \left\{
    \begin{array}{ll}
      0 & \mbox{if } w\cdot x + b \leq 0 \\
      1 & \mbox{if } w\cdot x + b > 0
    \end{array}
  \right.
\tag{2}\end{eqnarray}$

Perceptron bias is essentially a measure of how easy it is to get a perceptron to output a 1 or *fire* to put it in terms of a biological neuron.

Perceptrons can also be used to compute logicals (`AND`, `OR`, `NAND`). Example:

![img](http://neuralnetworksanddeeplearning.com/images/tikz2.png)

This perceptron has each weight as -2 and an overall bias of 3. So if we input 00 then it produces 1 since `(-2)*0 + (-2)*0 + 3 = 3` is positive. Inputs of 10 or 01 also result in 1 but 11 outputs 0 because the result is negative (walk through math on your own). This is therefore a [`NAND`](https://en.wikipedia.org/wiki/NAND_gate) gate.

`NAND` gates tend to be universal for computation because any computation can be built out of `NAND` gates.

When drawing perceptrons, it is typical to include the *input layer* as so

 ![img](http://neuralnetworksanddeeplearning.com/images/tikz6.png)

### Sigmoid Neurons

What we want is for a small change in the learned weights or biases to cause only a small change in the output from the network. This doesn't happen however when we use perceptrons. Small changes in weights or biases of any single perceptron an cause the output from that perceptron to completely flip. This makes it difficult to gradually modify the weights and biases so that the network gets closer to the desired behavior.

Sigmoid neurons are one way to overcome this. They are similar to perceptrons but modified so that small changes in weights/biases only cause small output changes. So while perceptrons can take on values of 0 or 1, sigmoid neurons can take on any continous value, say 0.638. Sigmoid neurons also have weights for inputs $w_1, w_2, \ldots$ and bias $b$ like perceptrons but instead of output being equal to 0 or 1, it is now $\sigma(w \cdot x+b)$ where $\sigma$ is the sigmoid function defined as:

$\begin{eqnarray}
  \sigma(z) \equiv \frac{1}{1+e^{-z}}.
\tag{3}\end{eqnarray}$


You can rewrite this equation with inputs $x_1, x_2, \ldots$ as so:
$\begin{eqnarray}
  \frac{1}{1+\exp(-\sum_j w_j x_j-b)}.
\tag{4}\end{eqnarray}$
