
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

Maybe in the original vector yoyve got info about MJ . After the MLP operations the operation vector might info include info somehwat connected to basketball. Now when iriginal vector and the operation vector gets added the final result vecot contains ALL INFO ,,,, MJ and 