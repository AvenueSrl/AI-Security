
During several tests researchers have come to a conclusion that facts live inside Multi layer perceptron I suppose 

Esier computation compared to the attention block.

THe computer involves two matrices (Linear) with a simple smething in between 

Though the structure is simple the behaviour  is challenging to undrtand whoch might lead to emergent behaviours 

![[Pasted image 20251007173920.png]] 

In a multi layer  perceptron nah all thses vectors which originally eant the input text are sent inside from a previous attention block after sending in these will  go through a series of operations and at the end an vector of the same size as the parent vector is found ''

![[Pasted image 20251007174306.png]]


![[Pasted image 20251007174326.png]]


After the operations are done no the original vector is added to the opertaion vector and the sum is the result that flows out 

IN mlp all of thses happen parallely ok . for all vector sequences ... In short the vectors dont really talk to each other in this step 

![[Pasted image 20251007174735.png]]


For example here you want to store the fact MJ plays Basketball

Maybe in the original vector yoyve got info about MJ . After the MLP operations the operation vector might info include info somehwat  - It will have direction info corresponding to the bare vector basketball connected to basketball. Now when iriginal vector and the operation vector gets added the final result vecot contains ALL INFO ,,,, MJ and Basketall 

![[Pasted image 20251007175327.png]]

First step in the mlp the original vector gets multiplied with a very large matrix - this matrix contains ontains all the model parameters used to tune the model ok 
![[Pasted image 20251007175540.png]]


Think of each row of the model parameter matrix as its own vector and we are doing dot product eith the embedding ( which is the original vector

![[Pasted image 20251007175811.png]]

For example here we can see that only if the vector encodes both MICHAEL AND JORDAN will its value be 2 otherwise when the other vetcors are checked thier values will be in 1 or less than 1 . Ok

Similarly you can think of the other Rows asing  other different questions about the nature of the inquiry . For example Is it a man? Is it metallic? All of thses question help a lot trust me?

That is probing at some other types of features of the vector being processed

Very often you'll add another matrix to the output whoch is leanrt from the training data 

This another matrix is knwn a the BIAS

Of course! That's an excellent question that gets to the heart of how neural networks learn.

In a Multi-Layer Perceptron (MLP), the **bias** is an additional, trainable parameter attached to each neuron (except the input neurons). Its primary role is to provide the model with **flexibility and the ability to fit the data better** by shifting the activation function to the left or right.

Let's break this down in detail.

---

### 1. The Analogy: The Y-Intercept

Think of the simplest model, a line: `y = mx + c`.
*   `m` is the weight (slope) – it determines the angle of the line.
*   `c` is the bias (y-intercept) – it determines where the line crosses the y-axis.

Without `c` (the bias), every line would be forced to go through the origin (0,0). This would be incredibly restrictive! The bias `c` allows us to shift the line up and down to find the best possible fit for the data.

A neuron in an MLP is a more complex version of this.

### 2. The Mathematical View: Inside a Single Neuron

A neuron in an MLP performs two steps:

1.  **Summation:** It calculates a weighted sum of its inputs.
2.  **Activation:** It applies an activation function (like Sigmoid, ReLU, Tanh) to this sum.

The formula for the output `z` of a neuron is:

**`z = activation( (w1 * x1) + (w2 * x2) + ... + (wn * xn) + b )`**

Where:
*   `x1, x2, ... xn` are the input values.
*   `w1, w2, ... wn` are the **weights** associated with each input.
*   `b` is the **bias**.
*   `activation` is the activation function.

The term inside the parentheses `(w1*x1 + ... + wn*xn + b)` is often called the "net input."

### 3. What Does the Bias Actually Do?

The bias allows the neuron to **activate (or "fire") even when all its inputs are zero.**

Let's see why this is crucial:

*   **Without Bias:** The output of the summation is `w1*x1 + w2*x2 + ...`. If all inputs (`x`) are zero, the output is forced to be zero *before* the activation function. The decision boundary (the line or curve that separates classes) is forced to pass through the origin of the feature space.
*   **With Bias:** The output is `w1*x1 + ... + b`. Even if all inputs are zero, the output is `b`. This means the decision boundary can be shifted anywhere, not just through the origin.

**A Simple Example: The AND Gate**

Imagine we want an MLP to learn the AND logic function:

| Input 1 | Input 2 | Output |
| :-----: | :-----: | :----: |
|    0    |    0    |   0    |
|    0    |    1    |   0    |
|    1    |    0    |   0    |
|    1    |    1    |   1    |

We can model this with a single neuron (a Perceptron) using the `step` activation function (outputs 1 if input > 0, else 0).

We need to find weights (`w1`, `w2`) and a bias (`b`) so that:
*   `w1*0 + w2*0 + b <= 0`  -> Output 0
*   `w1*0 + w2*1 + b <= 0`  -> Output 0
*   `w1*1 + w2*0 + b <= 0`  -> Output 0
*   `w1*1 + w2*1 + b > 0`   -> Output 1

It's impossible to solve this without a bias! Try it. Any line `w1*x1 + w2*x2 = 0` that goes through the origin cannot separate the point (1,1) from the others.

**With a bias, we can find a solution.** For example: `w1=1, w2=1, b=-1.5`.
*   For (1,1): `(1*1 + 1*1) - 1.5 = 0.5 > 0` -> Output 1.
*   For (0,1): `(1*0 + 1*1) - 1.5 = -0.5 <= 0` -> Output 0.

The bias `b = -1.5` shifted the decision boundary so that only the (1,1) input produces a positive net input.

### 4. Key Properties of the Bias

1.  **Trainable Parameter:** Just like weights, the bias is learned during the training process (via backpropagation and gradient descent). The algorithm adjusts the bias to minimize the error of the network.
2.  **Per Neuron:** Each neuron in the hidden and output layers has its **own** unique bias value. This gives each neuron independent control over how it shifts its activation function.
3.  **No Input Connection:** The bias is not connected to any previous neuron. It's a constant value that is added to the sum.

### 5. Why is it So Important?

Without bias, an MLP would be a series of linear transformations, even with activation functions in between. The bias is fundamental to the network's ability to:
*   **Learn Complex Patterns:** By shifting activation functions, the network can create more complex, non-linear decision boundaries.
*   **Improve Model Fit:** It prevents the model from being "locked" into a specific position (passing through the origin), allowing it to fit a much wider variety of datasets.
*   **Achieve Universal Approximation:** The theoretical proof that MLPs can approximate any function relies on having biases in the neurons.

---

### Summary

| Feature | Weight | Bias |
| :--- | :--- | :--- |
| **Purpose** | Controls the **influence** of an input. | Controls the **threshold** for activation. |
| **Analogy** | The **slope** of a line (`m` in `y=mx+c`). | The **y-intercept** of a line (`c` in `y=mx+c`). |
| **Effect** | Determines how sensitive the neuron is to a specific input. | Shifts the activation function left or right. |
| **Necessity** | Allows learning relationships between inputs and outputs. | Allows the model to fit data when all inputs are zero or to create offsets. |

In short, the **bias is a crucial, trainable parameter that gives each neuron in an MLP the freedom to activate independently of its inputs, dramatically increasing the model's learning capacity and flexibility.**


![[Pasted image 20251007180746.png]]

Now there is  a terrible problem 
As we know the present process is extremely linear. IF our vector is high eniugh it might get triggered by similar yet totally unneeded  vectors like in this case Alexis jordan and what not ..


To prevent we need something that provide a concrete anwer whether the given vector is Michael jordan r not .  To d this we pass this vector  through some Non linear function RELU 

![[Pasted image 20251007181323.png]]

A comman non linear function maps the negative number to 0 and the positive numbers remain unchanged

![[Pasted image 20251007181524.png]] 

Models also Something called Gelu - WHich is the similar but have a smoother shape compared 

Also in the previous exmaple nah After adding the bias for this example the top value fo the vector is 1 f the vectr corresponds to michael jordan 

Basically this Relu acts like a AND gate - Itll check whether its actually Michael jordan or not .

![[Pasted image 20251007182505.png]]


Usually representation of mlps reprsent this matrix multiplication  and relu fucntion . 

Like i said after passing through the ReTU the neuron is said to be active of that First valueo in the vector is 1 or else its inactive if the value is anything else (0)

![[Pasted image 20251007182944.png]]

After the Rel function we  again multiply the vector bu a large matrix then add the bias vector..... Here after doing this nah the resulting matrix is bakc to the rginal embedding matrix value 

Here since its reduced we can call this large matrix and down scaler 

We can think of it here as each column of the down scaler is dot produted  with the row. 


Heres how it works when the first value is 1 it corresponds to Michael Jordan then that particlaur neuron is active. Then we'll add that neuron value to the final result 

![[Pasted image 20251007183858.png]]

The activation of a neuron tells you how exactly a given vector aligns with the direction of a desired THING - God i suck at english 


Coulmns of the secod matrix tekll you what will be added to that neuron if it does end u being active 


Until now when we think we of a ector we think of it s it cleanly encodes a a sibgle word


