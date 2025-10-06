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
