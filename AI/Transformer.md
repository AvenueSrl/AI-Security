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

![[Pasted image 20250929185856.png]]

dimension x tokens give the exact weights 


vectors contain more information than just the ord themselves . they encode information about the position of the word . they have the capacity to soak in  information .

A vector can be progrssively be ulled and ushed being influenced by other vectirs giving it a more numanced meaning it can predict the next word in the context more efficiently . 

Before attention block each vector is conceptualised to a single word with no regards for its cntext 


The network ccan only process a fixed number f contexts at a time and it called context size ---- REMEMBER THE DUMB C.AI MODELS?/


Conetxt size limits how much  words a transformer can incorporate when its makeing the rediction of the net word 

Remember at the very end we want a probability distribution of the next word ![[Pasted image 20250929191112.png]]


Over here a well trained model on HP wil look at th key words or tokens and give high prediction for snape .... Lets see hoe this ahppens 


![[Pasted image 20250929191223.png]]



Firts another vector is used that maps the very last vector to the vocabulary matrix of the LLM . Each token has a value in that matrix 

Then theres a function that normalises this into a probability distribution 
![[Pasted image 20250929191500.png]]


Such a normalising function is callled softmax


NOWWWWWWW why do we use the last matrix of the embedded matrix  exactly 

Each vector in the final layer makes a prediction for the vector after it . THe combined predctuon of the all of them only we are taking at the very end 

![[Pasted image 20250929192019.png]] 


this matrix is called the unembedding matrix and we give it th abel Wu
Unembedding has the same dimension as teh embedding 


SOFTMAX 

USUALLY WHEN YOU WANT A LIST OF VALUE TO BE USED FOR PREDICTION IN PROBABILTRY DENSITY FUNCTION NAAAA WE REQUIRE THE VALUE TO BE BETWEEN 0 AND 1. all the values should add up to 1.... HOWEVER WHEN YOU DO THE MATRIX VECTOR MULTIPLICAtion this is not true whatsoever .

softmax is a way in which you turn a arbitrary list of numbers into you know valurs between o and 1. the higher number end u closer to one . 
![[Pasted image 20250929192758.png]]

heres how the softmax function works . You take e to rhe power of value and divide it to the sum of all e to the power of x value . this will  normalize it ok 
![[Pasted image 20250929193050.png]]


Heres how temperature works it is the denominator in the softmax function. When the T is large  more weight its given to smaller values you know its adds in a little more spice. Less T moeans the model is more predictabl e


that +6.0 -5.0 inputs are called AS LOGITS OK



WHEN T IS WAY TOO LARGE THE MODEL DELVES INTO NONSENSE











