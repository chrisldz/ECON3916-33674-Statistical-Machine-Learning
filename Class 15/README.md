This project explores the bias-variance tradeoff through polynomial regression using both synthetic and real-world data. I first generated sine-wave data with noise (n=50 training, n=200 test) to visualize how model complexity affects performance. As the polynomial degree increased, the model transitioned from underfitting to overfitting, which was clearly reflected in the complexity curve where training error decreased while test error followed a U-shape.

To select the optimal model, I implemented 5-fold cross-validation and showed that the CV-selected degree closely matched the true test-optimal degree. This demonstrates how cross-validation can be used as a reliable model selection tool without accessing the test set.

I then applied the same ideas to the Ames Housing dataset (1,460 observations, 80 features). Comparing a full “kitchen-sink” model to a simpler model using the top 5 correlated features, I found that the simpler model achieved better CV RMSE despite having lower training R-squared. This highlights how more complex models can overfit and perform worse on unseen data.

Overall, this project demonstrates the importance of balancing model complexity and using cross-validation to improve generalization.
