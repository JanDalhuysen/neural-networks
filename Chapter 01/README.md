# Brain.js

## What is Brain.js

[brain.js](https://brain.js.org) is a GPU accelerated library for [Neural Networks](http://en.wikipedia.org/wiki/Artificial_neural_network) written in [JavaScript](https://en.wikipedia.org/wiki/JavaScript)

### Here's an example showcasing how to approximate the XOR function using brain.js

```javascript
const config = {
  binaryThresh: 0.5,
  hiddenLayers: [3],
  activation: "sigmoid",
  leakyReluAlpha: 0.01,
};

const net = new brain.NeuralNetwork(config);

const trainingData = [
  { input: [0, 0], output: [0] },
  { input: [0, 1], output: [1] },
  { input: [1, 0], output: [1] },
  { input: [1, 1], output: [0] },
];

net.train(trainingData, {
  log: (error) => console.log(error),
  logPeriod: 100,
});

console.log(net.run([0, 0]));
```

### Output

```powershell
{error: 0.25814613552088606, iterations: 100}
{error: 0.25792675802481657, iterations: 200}
{error: 0.2577326665393045, iterations: 300}
{error: 0.2575609914735839, iterations: 400}
{error: 0.2574081577635088, iterations: 500}
{error: 0.25727035488078887, iterations: 600}
{error: 0.25714386405788936, iterations: 700}
{error: 0.25702534743908423, iterations: 800}
{error: 0.2569117217749346, iterations: 900}
{error: 0.2568000323138184, iterations: 1000}
{error: 0.2566871551466887, iterations: 1100}
{error: 0.25656939288717506, iterations: 1200}
{error: 0.25644162234840717, iterations: 1300}
{error: 0.25629573848741605, iterations: 1400}
{error: 0.2561176955546127, iterations: 1500}
{error: 0.2558808957106429, iterations: 1600}
{error: 0.2555307697528575, iterations: 1700}
{error: 0.2549471887880106, iterations: 1800}
{error: 0.2538553243546975, iterations: 1900}
{error: 0.25164116138044434, iterations: 2000}
{error: 0.24709035303451454, iterations: 2100}
{error: 0.2382807842646919, iterations: 2200}
{error: 0.2237342834342524, iterations: 2300}
{error: 0.2062758532436597, iterations: 2400}
{error: 0.19102335688381555, iterations: 2500}
{error: 0.17839612904458152, iterations: 2600}
{error: 0.1658798183788488, iterations: 2700}
{error: 0.15029786759121505, iterations: 2800}
{error: 0.12813729732833595, iterations: 2900}
{error: 0.10048281802964337, iterations: 3000}
{error: 0.07431854218604994, iterations: 3100}
{error: 0.05376608374089514, iterations: 3200}
{error: 0.03903716132072166, iterations: 3300}
{error: 0.028943838835498795, iterations: 3400}
{error: 0.022096467412897072, iterations: 3500}
{error: 0.017385625259823123, iterations: 3600}
{error: 0.01406036935639883, iterations: 3700}
{error: 0.01164440685877223, iterations: 3800}
{error: 0.009839250461507201, iterations: 3900}
{error: 0.008455668209611078, iterations: 4000}
{error: 0.007371049577060723, iterations: 4100}
{error: 0.0065037807436825745, iterations: 4200}
{error: 0.005798163991338163, iterations: 4300}
{error: 0.005215400157032105, iterations: 4400}

Float32Array
[0.05661680921912193,
buffer: ArrayBuffer(4),
byteLength: 4,
byteOffset: 0,
length: 1,
Symbol(Symbol.toStringTag): 'Float32Array']
```
