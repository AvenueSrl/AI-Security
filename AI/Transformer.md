Dall e and Modjpurney are based on Tansformers 


Thiugh Trabsfirmers has multiple use cases - Chatgot is built on a one that you know ...... Gtes in a string then then bssed on context or whatevr it predics what exactly comes after it 

That prediction takes the form of s probabltly distribution 

. Basically what it does is that it predicts  a small part join it with teh irginal snaippet then the entire is thing s sent back intp the transformer and  then new words just follow 

This is repeated predicton and sampling whoch s what actually happens in chatgpt 

Heres how such LLMS work 

So essentially each input be it strings , videos and audio is dovided into smaller chunks called token - these tokens are then assigned a vector ... These vector can be visualized as a vecor in the 3d space . 

When Each vector is plotted words with similar meaning tend to be closer to each other on that 3d graph 

Immediate;y thses tokens arw sent to something called as attention block . In here the vectors communicate to each other and then update theor values accordingly

The attention block is responsible fr the contxt of each word


for eg model has different value in attention block in Machone learning model and amother in fashion model 

Relevant meanings and how exactly that meaning should be updated,

Meaning is somehow entirely encoded insode those vectors 


After attention block all blocks go rhrough something callede multileavel perceptron. Multilevel perceptron or forward feed layer. 

What exactky happens is that all vectors go through the same process parallely. This part can be summarized as each veator is asked a set of questions and the vectors are clasified accordingly 

Inside the Vectors undergo a process very similar to Matrix multiplication 

The vestors undergo attention blocks and mlp over and over agaon until the meaning is hopefully backed obto the last vector in the sequence 


This last  vector is then taken out a series of steps are performed in order to get a  probablity distributin of all possible vectors 


