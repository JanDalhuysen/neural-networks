# Brain.js

## What is Brain.js

[brain.js](https://brain.js.org) is a GPU accelerated library for [Neural Networks](http://en.wikipedia.org/wiki/Artificial_neural_network) written in [JavaScript](https://en.wikipedia.org/wiki/JavaScript)

### Here's an example using strings

```javascript
const net = new brain.recurrent.LSTM();

const trainingData = [
  "doe, a deer, a female deer",
  "ray, a drop of golden sun",
  "me, a name I call myself",
];

const result = net.train(trainingData, {
  iterations: 1500,
  log: (details) => console.log(details),
  errorThresh: 0.011,
});

console.log("Training result: ", result);

const output = net.run("doe");
console.log(output);
```

### Output

```powershell
iterations: 0, training error: 0.2643063308455283
iterations: 10, training error: 0.13712005626014992
iterations: 20, training error: 0.07606445345328039
iterations: 30, training error: 0.06114421055249688
iterations: 40, training error: 0.029531350150397498
iterations: 50, training error: 0.02161509832012849
iterations: 60, training error: 0.01569867384634158
iterations: 70, training error: 0.013650863890901005
iterations: 80, training error: 0.01273646466654219
iterations: 90, training error: 0.019207668822300888
iterations: 100, training error: 0.01238531896770251
iterations: 110, training error: 0.0117546771980326
iterations: 120, training error: 0.011366218535672564
iterations: 130, training error: 0.011136528835120058

Training result:
, a deer, a female deer
```
