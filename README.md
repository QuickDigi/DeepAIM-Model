# DeepAIM-Model

## Overview  
**Model.json** is a pre-trained AI model based on **LSTM** or **GRU**, designed for processing structured conversational data, including **categories, emotions, questions, answers, reasons, and scold responses**.

## Installation  
1. Download **Model.json** and place it in your project directory.  
2. Load the model using **TensorFlow.js** or **Brain.js**.

## Usage  
### Loading the Model  
#### TensorFlow.js  
```js
const model = await tf.loadLayersModel('Model.json');
```
## Brain.js
```js
const brain = require('brain.js');
const fs = require('fs');

const rawData = fs.readFileSync('./Model.json');
const modelData = JSON.parse(rawData);

const net = new brain.recurrent.LSTM();
net.fromJSON(modelData);
const input = "your sequence input";
const output = net.run(input);

console.log(JSON.stringify(output, null, 2)); // Structured output
```

### Making Predictions
## TensorFlow.js

```js
const inputTensor = tf.tensor(/* Input data */);
const output = model.predict(inputTensor);
console.log(output.arraySync()); // Ensure readable output
```
