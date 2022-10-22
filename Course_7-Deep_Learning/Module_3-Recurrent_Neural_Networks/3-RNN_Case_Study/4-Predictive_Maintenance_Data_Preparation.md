# Predictive Maintenance - Data Preparation

After loading the data into the colab notebook, you will also need to pre-process the data to get it in the required format before using it for our model.

**VIDEO**

You saw that the target feature is derived from column ‘cycles’ of the actual data set. Since the maximum number of cycles given in the data set corresponds to its failure point, you can directly calculate the remaining number of cycles or remaining useful life (RUL) for engines.

**Training data labeling**  
Lets see an example, where we have engine 1 with maximum number of cycles as 192. If at the current time step, this engine has run for just one cycle, it will have another 191 cycles. Similarly if at current cycles are 2, the remaining useful life will be 192-2 = 190.

After calculating this we convert this variable into binary type considering if the engine failed within w1 number of cycles. For example if w1 = 30 and engine1 has only 20 remaining cycles (RUL), then the target label will be 1. At another time step engine1 might have 35 remaining cycles (RUL) then the target label will be 0.

**Test data labeling**  
You have a remaining truth table along with the actual test data. The maximum number of cycles in the test data won’t denote the failure points, as they will have corresponding remaining number of cycles after the max number of cycles of the test data. For example, suppose the maximum number of cycles of engine1 are 35 according to the test data and the remaining number of cycles are 20 according to the truth data, then the total maximum number of cycles for engine1 will be 35+20=55. Now at time t (when the engine has already run for t cycles), the remaining useful cycles (RUL) will be 55-t. For example when the engine has already run for 2 cycles, the number of remaining cycles will be 55-2=53.

We further process this RUL to attain a binary target variable similar to what we did in training data.

In the next step, you will see a sequence generating function, which will help you build the model further.

**VIDEO**

In the next segment, you will learn how to build an LSTM model for our problem statement.