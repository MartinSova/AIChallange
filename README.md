## Language Detection Challenge
#### *Martin K. Sova*

## The problem

"European Parliament Proceedings Parallel Corpus is a text dataset used for evaluating language detection engines. The 1.5GB corpus includes 21 languages spoken in EU.  

Create a machine learning model trained on this dataset to predict the following test set." (https://fellowship.ai/challenge)

## Motivation

After carefully considering each of the 5 challenges offered by the fellowship program, I have decided to complete the third challenge titled "Language Detection". All 5 challenges seem both interesting and demanding, but after giving some thought to the requirements of each challenge, I had decided that the Language Detection challenge suits my interest the best and would allow me to work with the tools and the model that kindled a particular curiosity in me.

The details of how I addressed and completed this challenge are outlined thoroughly throughout the project; this provides an overview of my solution to the problem, which, in turn, gives context to why I found this challenge so engaging. The project details below are supplementary to the more extensive documentation that can be found in the *MSova_The_Language_Detection_Challenge* file.

## The model of choice

The model of choice was multinomial logistic regression. To account for the problem of overfitting the training data, I use multinomial logistic regression with L2 regularization, which aids in handling correlated features. Further, L2 regularization shrinks the regression coefficients and accounts for sparsity. Logistic regression alone demonstrates longer training time to train the multinomial logistic regression model and would not perform well if the features used to train it are highly correlated. For these reason, L2 regularization is advantageous. To prevent the assumption of statistical independence of the input random variables, the multinomial logistic regression is preferred over naive Bayes classifiers.

## Conclusion and future work

As a result of adjusting hyperparameters, we observe that the character frequency analysis yields a higher prediction accuracy than word frequency analysis in language detection. The importance of denoising from punctuations and digits is imperative as these are orginary symbols across most languages, and therefore should be treated as noise in the training data; this is to adhere to the idea that learning to distinguish between languagues is not about the vocabulary, but rather the the disassociation between the script of a language. We observe that multinomial logistic regression performed poorly for similar languages, such as in the case of Czech and Slovak and Spanish and Portuguese, which were often missclassified.

In the future, we should look to imporve the 4-gram character analysis model by leveraging a grid-search method, which aids in finding the best model hyperparameters. Alternatively, we could also use higher n-gram models but we would have to consider the high computational time necessary to train such a model on a regular PC; in such case, we could train the model using GPU rather than CPU. There are other enticing solutions, such as utilizing Recurrent Neural Networks, which, although may perform better, may be too computionally expensive to train large datasets such as the European Parliament Proceedings Parallel Corpus, rendering the increase of prediction accuracy trivial.





