# Chapter 1
## Using neural nets to recognize handwritten digits
### Neural networks vs. human brain
Neural nets use training examples to automatically infer rules for recognizing handwritten digits. This requires large numbers of examples to increase accuracy. Human brains are more like a model pretuned to process images and patterns.

### Perceptrons
- Type of artificial neuron
- Not as commonly used as compared to sigmoid neurons

A perceptron takes several binary inputs, ![img1](http://www.sciweavers.org/tex2img.php?eq=x_1%2C%20x_2%2C%20%5Cldots&bc=White&fc=Black&im=jpg&fs=12&ff=arev&edit=0) and produces a single binary output:
![alt text](http://neuralnetworksanddeeplearning.com/images/tikz0.png)

So in this example, the perceptron has 3 inputs ![img2](http://www.sciweavers.org/tex2img.php?eq=x_1%2C%20x_2%2C%20x_3&bc=White&fc=Black&im=jpg&fs=12&ff=arev&edit=0). The importance of these inputs to the corresponding output are denoted as weights ![img3](http://www.sciweavers.org/tex2img.php?eq=w_1%2Cw_2%2C%5Cldots&bc=White&fc=Black&im=jpg&fs=12&ff=arev&edit=0) which are real numbers. The neuron then outputs 0 or 1 which is determined by whether the weighted sum ![img4](http://www.sciweavers.org/tex2img.php?eq=%5Csum_j%20w_j%20x_j&bc=White&fc=Black&im=jpg&fs=12&ff=arev&edit=0) is less than or greater than some threshold value. Algebraically:
![img](http://www.sciweavers.org/tex2img.php?eq=%5Cbegin%7Beqnarray%7D%0A%20%20%5Cmbox%7Boutput%7D%20%26%20%3D%20%26%20%5Cleft%5C%7B%20%5Cbegin%7Barray%7D%7Bll%7D%0A%20%20%20%20%20%200%20%26%20%5Cmbox%7Bif%20%7D%20%5Csum_j%20w_j%20x_j%20%5Cleq%20%5Cmbox%7B%20threshold%7D%20%5C%5C%0A%20%20%20%20%20%201%20%26%20%5Cmbox%7Bif%20%7D%20%5Csum_j%20w_j%20x_j%20%3E%20%5Cmbox%7B%20threshold%7D%0A%20%20%20%20%20%20%5Cend%7Barray%7D%20%5Cright.%0A%5Ctag%7B1%7D%5Cend%7Beqnarray%7D&bc=White&fc=Black&im=jpg&fs=12&ff=arev&edit=0)
