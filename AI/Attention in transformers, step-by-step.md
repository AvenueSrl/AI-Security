First developed n a 2017 paper called attention is all you need

When the tokens are first created theyre are merly lookup table with no reference to context 

Its only in the next step that the surrounding embeddigs have the ability to pass info to each other making them more richer 

A well trained attention block calculates how much you need move this genrnic embedding to a diretion which is more suitable to the context 

Attention block helps to share the meaning across longerdustances making it more richyer than the neaning of a single word 

Thats 3hy thr last vector nah that we use for predicting the word somehow conceptualises the entire context of it

An **attention head** in [Transformer models](https://www.google.com/search?client=opera&q=Transformer+models&sourceid=opera&ie=UTF-8&oe=UTF-8&mstk=AUtExfDLfWSwjEPdjGG-ZpW6GUY9Pe3iHUQZkYkzvGuCZUWZtwte6fE2oyifqlV2DE8a0anJ5aoTfizpmYad_RZnr7WyF8lC4c7eNngaJ3gs_TcYtuNU_IrEQulJPNFiANcEO_dIaTGJwy--bdjlphObzVl8IYeVHFGNRzgcoGCoJoBaSYfU274uzjb9mrABQG4ksjMnWGNOfd7LO3-t96kpU-BxL5K3SJ0_lUg42IyoWaMmgKL6Q6R1e3bHqez2lD7fJjrmgyu0E9GxFLm4JtIRPBa7&csui=3&ved=2ahUKEwi0_qvRw4-QAxU4SGcHHdj0AbYQgK4QegQIARAD) is ==a parallel instance of the self-attention mechanism that allows the model to process different parts of the input sequence and capture diverse relationships between tokens simultaneously==

Inside every Attention head is a series of matrix mutiplication thereby trying to ingest the proper meaning of a provided word with its context 


The true behaviour is hard to understabd cause youre tweaking a lot of parameters to reduce cost function 

![[Pasted image 20251006173636.png]]

For example over here for the first query matrix youre taking a noun figuring out the adjective in front of it and then computing all that info into a matrix smaller than the actual embedding matrix 

![[Pasted image 20251006175522.png]]

This query matrix is the product of the matrix Wq with embedded matrix 


the entries of wq are the parameters of the model 

Theres a second type of matrix called the key matrix which you multiply by each one of the embeddings yeaahhh


Keys match the queries when they closely align with each other 

To measure how well each key matches a query we use dot product of key query 

The larger the dot product the bwtter the key alogns wth the query - This is called Attending to 

Small or  negative means they are unrelated to each other 

![[Pasted image 20251006180345.png]]

THis key query calculation basically tells us how relavant each word is to influence the other word in the context 

Now as you cn see we dont want a scattered values for - infinity to + infinity

We need to normalise it , Basically convert it to a proo=bality distribution form 0 to 1 and when you add all of the values we need to get 1 

So we compute a softmax along all of these columns 
![[Pasted image 20251006180815.png]]

After softmaxing we get te attention pattern much better reprsentatiob 

![[Pasted image 20251006180950.png]]

Here Q is for querys K is for keys okkkk..... 

kTq is the compact way to represent all the dot products of keys and queries ...


for numerical stability we divide all the dot pdts of the square root of the dimension of that query space 


During the training process the mnodel and oarameters are tuned deoending on how high the probabilty is given  to the true next word of the training oassage 


Apparently the efficiency pf the model increases when you make it predict from the beginning and build upon it like here 

![[Pasted image 20251006181517.png]]

this mutliple predictions happen parallely .

One important thing is that you ont allow later words to influence earlier words ans that would  nlt really be training?

![[Pasted image 20251006181820.png]]


To prevent this we want the values that influence the earlier words from the later words to be somehow be foeced to 0.

You cant just set it to 0 as it would unnormalize it. So instead you put them as negative infity so after softmaxing they would ayutomatically be turned to 0 and reamin normalized 


THIS PROCESS IS CALLED MASKING 


ATTENTION PATTERNS SIZE IS EQUAL TO THE SQUARE OF THE CONGTEXT SIZE --- WHICH IS CONTEXT SIZE IS A HUGE BOTTLE NECK FOR LLMS 

![[Pasted image 20251006182355.png]]


THESE WERE BUILT TO MAKE TGE CONTEXT SIZE MORE SCALABLE 


nOW HOW DO THSES WORDS COMMUNICATE AND INFLUENCE EACH OTHER ??

ONE STRAIGHTFORWARD WAY IS TO JUTS A VALUE MATRIX - tHE FIRST ENBEDDING IS MUTIPLIED WITH THE VALUE MATRIX AND THAT RESULT IS ADDED TO THE SECIBD MATRIX 


![[Pasted image 20251006182739.png]]


