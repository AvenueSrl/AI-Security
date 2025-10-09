
Look forst a noisy image is  extracted ok and then its apassed through a transformer and you get a slightly clear yet still noisy  image . The noisy image result is added to the original noise and this new model is then sent back into the trasgormer this time itll provide a clearer image 

Eventually i suppose the noise is extemely random 

Let us take an exmaple of CLIP - Clip is both a Language model and a vision model .


it basically collarbotes both image and its correpsonding meaning say in a high dimensional soace A mans picture and the man letter vector might be in the same direction in a higher dimensional space 


At a high leavel Diffusion Models are trained to remove noise from a image alright 

Diffusion models are kind of inspired by diffusion process in physics 

So basically CLIP has one goal - Youre given a text - the vector encoding that text should be similar to the encoded vector that is given out of the text descripted image ...

![[Pasted image 20251009182049.png]]


In the CLIP Model when the vetros ofo the image captions are placed row by olumn ... the entries in a diagnol correspond to the crrect correlation . the others are incorreect . 

The objective of clip is maximize this correct correlation and  minimize the selction of incorrect correlation 

How do ou measure the similarlity f a text vector and a image vector - using the cosine similarity 
![[Pasted image 20251009182600.png]]

The cosine Similarity basically tell you te cos angle between two vector in that higher  dimensional space . The more alignd and siilar two vectros are thr more maximum the cos angle will be 


For related the CLIP aims to maximize and for Unrealted CLIP aims to mimimize 

![[Pasted image 20251009183357.png]]


Over here we can see two vectors one corresponding tona man waering a hat and not waering a hat . Then a difference vector is calculated . now that vector and the cosine angle with other word evctors are found ... THis is will us classify this particular 