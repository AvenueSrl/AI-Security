
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

Similalry you can think of the other Rows asing  other different qyestionsabout the nature of the inqu

