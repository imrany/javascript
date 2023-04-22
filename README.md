# Insult checker
Checks input as insult or not using brain.js

# Using Natural
Certainly! Here's an example that uses the natural library in Node.js, which provides a range of natural language processing tools including a Naive Bayes classifier for text classification:
```js
// Import natural library
const natural = require('natural');

// Create and configure the NaiveBayes classifier
const classifier = new natural.BayesClassifier();

// Define the training data
const trainingData = [
  { text: "You are stupid", label: "insult" },
  { text: "I like your shirt", label: "non-insult" },
  // Add more labeled examples to your training data
];

// Train the NaiveBayes classifier
trainingData.forEach(data => classifier.addDocument(data.text, data.label));
classifier.train();

// Test the NaiveBayes classifier with some input data
const input = "You are so annoying";
const output = classifier.classify(input);

// Output the prediction
if (output === "insult") {
  console.log("Input is an insult");
} else {
  console.log("Input is not an insult");
}
```
In this example, we create an instance of the natural.BayesClassifier class, which represents a Naive Bayes classifier. The training data is defined with labeled examples of input text samples, where the text property contains the input text and the label property contains the class label (insult or non-insult). The classifier.addDocument() method is used to add each training example to the classifier, and the classifier.train() method is called to train the classifier.

You can then use the classifier.classify() method to make predictions on new input text samples. The predicted class label (insult or non-insult) is returned, and you can use it to output the prediction accordingly.

Note that the Naive Bayes classifier is a simple probabilistic model that assumes independence between features, and may not always capture complex patterns in the input text data. It's important to experiment with different classifiers and fine-tune the model to achieve the best possible results for your specific use case. Additionally, as with any machine learning model, proper text preprocessing techniques may be necessary to achieve better classification accuracy, depending on the specific characteristics of your dataset.

#Using Brain.js
```js
// Import brain.js library
const brain = require('brain.js');

// Create the LSTM neural network
const lstm = new brain.recurrent.LSTM();

// Define the training data
const trainingData = [
  { input: "You are stupid", output: "insult" },
  { input: "I like your shirt", output: "non-insult" },
  // Add more labeled examples to your training data
];

// Train the LSTM neural network
lstm.train(trainingData, { iterations: 1000 });

// Test the LSTM neural network with some input data
const input = "You are so annoying";
const output = lstm.run(input);

// Output the prediction
if (output === "insult") {
  console.log("Input is an insult");
} else {
  console.log("Input is not an insult");
}
```
In this example, we create an instance of the brain.recurrent.LSTM class, which represents a Long Short-Term Memory (LSTM) recurrent neural network. The training data is defined with labeled examples of input text samples, where the input property contains the input text and the output property contains the class label (insult or non-insult). The lstm.train() method is called to train the LSTM neural network with the training data, and we specify the number of iterations for training (in this case, 1000 iterations).

You can then use the lstm.run() method to make predictions on new input text samples. The predicted class label (insult or non-insult) is returned, and you can use it to output the prediction accordingly.

Note that this is a basic example and may not be suitable for all text classification tasks. Fine-tuning of hyperparameters, adjusting the architecture of the LSTM network, and proper text preprocessing techniques may be necessary to achieve better classification accuracy, depending on the specific characteristics of your dataset. It's important to experiment and optimize the model based on your specific requirements to achieve the best possible results.