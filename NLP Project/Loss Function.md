Loss function are used to measure how far off a model's prediction is from the truth. For example, for the [[LeFlow Mini Project]], we want the model to 'look' at a 7, and be able to tell how far off it is during training.

## Sparse Categorical Crossentropy 

Let's say it sees a seven and outputs

```python
[0.01, 0.02, 0.00, 0.03, 0.01, 0.00, 0.02, 0.88, 0.02, 0.01]
```

Meaning it's 88% confident about the digit being a 7. In the sparse categorical crossentropy function (SCC from now on), the true label used is just the single correct digit (7) instead of using one-hot encoding ([0,0,0,0,0,0,0,1,0,0]). This is more memory efficient.

So the SCC function takes the predictions, then looks at the position of the true label (0.88 regarding 7), and takes the negative logarithm of the value (-log(0.88)). This ensures that if the model is correct and confident, it gains small loss. If it's wrong, big loss
- Very confident and correct (ie 0.95) -> small loss: $-log(0.99) \approx 0.05$ 
- Unsure (ie 0.5) -> med loss: $-log(0.5) \approx 0.69$
- Confident but wrong (ie 0.1) -> big loss: $-log(0.1) \approx 2.3$

This can be used to show the model how wrong it is ( bad model >:( )