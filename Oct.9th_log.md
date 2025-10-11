## Daily Log
### Time
- 2025-10-09

### Workload
- 1. Implement function on lagging features
- 2. Apply hybrid models and recieve result of MAE = 0.87 and R_square = 0.91
- 3. Test simple Flask framework and print "Hello World!" on the front page.

### Problem shooting
#### 1. About shift() in Pandas
- shift() doesn't "drop" rows, it only repositions data while preserving the index.
- This keeps Dataframe shaping stable and timestamps consistent

#### 2. About align() in Pandas
- using when two Dataframes don't have identical indices, and want to synchroniz before applying operations like subtraction or correlation.

#### 3. About parameter "periods" in shift()
```python
   df.shift(periods=i+1)
   # creates lag features in the right temporal direction
```
- reverse version will cause data leakage to models since they will learn more data before training

#### 4. Dataframe.dropna(inplace=True)
- dropna() won't mutate the dataframe by defualt, so use "implace" to reamain changed.

#### 5. About PowerShell
- "pip.exe" isn't really "dynamical". It hard-codes the absolute path to the Python interpreter that creates it.
```bash
   python -m pip install <package>
```

#### 6. About Hybrid model training
- first train model 1 -> predicting $\hat{y}_1$
- second train model 2 -> predicting the residuals: ${r}$ $=$ ${y}$ - $\hat{y}_1$