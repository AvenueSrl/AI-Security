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

This is how prmpts work - It starts as a seed value for the transformer tp build upon

![[Pasted image 20250929180933.png]]

At a base in linear regression We have two parameters - this helps to guide  the predictions . Similarly gpt 3 has 175 billion parameters 

Rememeber in all input processing its done by matrix processing . Any input say an image is converted into sch matrixes - maybe even high dimensional matrixes - no the inout has to formatted as a array of real numbers 

When a higher dimensional array is being used for Input prcessesing its called tensor 


You see in early ai models we had rigid parmeters sort of simple if else programs . However in these days we used tunable parameter and feed it large amounts of data. This provides the same kind of output but is much more versatile 

These tunable parameters are also called weights or weighted sums 

Usually thses waieghts are packaged together as components in a matrix vector product 

The weights are the actual brain - they are the one learned  dueing training 

All LLMS have a predefined list of vocabulary 

![[Pasted image 20250929183237.png]]



Each token is taken into a matrix ok. Each matrix has the values of each word - it starts random but soon it changes according to context - remember attention blocks?

![[Pasted image 20250929183424.png]]

Label embedding as We

As we embed various words into these vectors and plot them .... as teh model finetunes itself the directions i which eth vector points towards gets its own semantic meaning 

But they are really complicated yeahj? gpt 3 has 12000 something dimensional vectors 


![[Pasted image 20250929184059.png]]


THe words closest to tower are in similar directions as you can all se

![[Pasted image 20250929184304.png]]

![[Pasted image 20250929184319.png]]
![[Pasted image 20250929184353.png]]
in order ot find the vector for queen you know we can use similar vectors like man and woman ( qyeen femeinine version of king )

In conclusion the model choose one direction to enclose geder information 

![[Pasted image 20250929185035.png]]


Similar examples 



DOT PRODUCT OF TWO VECTORS CAN BE THOUGHT OF AS WELL THEY ALIGN 

Geometrically dot product is positive when vectors are in similar directions 0 when perpendicular and negative when they point in opposite directiosn 

![[Pasted image 20250929185558.png]]


![[Pasted image 20250929185625.png]]

From this we can quantively measure how plural a model finds a word . all of thses plot show the die=rect the place where the word is located



THE EMBEDDING MATRIX IS THE FIRST PILE OF WEIGHTS IN OUR MODEL 

IT SHOWS HOW EXACTLY OUR WORDS ARE TURBED INTO THE VECTROS NAH 









