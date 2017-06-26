### Understanding CNN

This project aims to understand CNNs and how the paramters impact the results.

* **Initialization of weights:**  
Initializing weights with standard deviation of 0.1 yielded better results when ran for 500 iterations. 
Train data accuracy hit over 95% in just ~200 iterations. While it struggled to reach 95% when weights were initialized with stddev = 1.0 for 500 iterations.  
Train: 500: accuracy:0.992188 loss: 0.0615625  
Test: 500: accuracy:0.9771 loss: 0.0689539  
Layer arch:  
`CONV (stride=1)` -> `RELU` -> `CONV(stride=2)` -> `RELU` -> `CONV (stride=1)` -> `RELU` -> `FULLY-CONNECTED` -> `RELU` -> `FULLY-CONNECTED` -> `SOFTMAX` -> `OUTPUT`  


* **Playing with Stride**  
Changing stride from 2 to 1 in second conv layer. Not much difference in results:  
Train: 500: accuracy:0.992188 loss: 0.0277827  
Test accuracy:0.9745 loss: 0.0767132  
Layer arch:  
`CONV (stride=1)` -> `RELU` -> `CONV(stride=1)` -> `RELU` -> `CONV (stride=1)` -> `RELU` -> `FULLY-CONNECTED` -> `RELU` -> `FULLY-CONNECTED` -> `SOFTMAX` -> `OUTPUT`  


* **Adding max pooling layer**  
Adding maxpool decreased the accuracy to approx 98.5%.  
Train: 500: accuracy:0.984375 loss: 0.0902737  
Test accuracy:0.9717 loss: 0.0938389  
Layer arch:  
`CONV (stride=1)` -> `RELU` -> `MAXPOOL` -> `CONV (stride=1)` -> `RELU` ->  `MAXPOOL` -> `FULLY-CONNECTED` -> `RELU` -> `FULLY-CONNECTED` -> `SOFTMAX` -> `OUTPUT` 


* **Adding dropout**  
Train: 500: accuracy:0.976563 loss: 0.105949  
Test accuracy:0.9743 loss: 0.0844915  
Dropout is applied while training data.
