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

\begin{eqnarray}
  \mbox{output} & = & \left\{ \begin{array}{ll}
      0 & \mbox{if } \sum_j w_j x_j \leq \mbox{ threshold} \\
      1 & \mbox{if } \sum_j w_j x_j > \mbox{ threshold}
      \end{array} \right.
\tag{1}\end{eqnarray}
