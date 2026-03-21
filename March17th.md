#### 1. Unzip files in PowerShell
- Base
```bash
Expand-Archive -Path "C:\path\to\your\file.zip" -DestinationPath "C:\target\folder"
```
- Force
```bash
Expand-Archive -Path "C:\path\to\your\file.zip" -DestinationPath "C:\target\folder" -Force
```

#### 2. Init Anaconda in Powershell
```bash
cd C:\Users\UserName\[Install folder]\anaconda\Scripts
& "C:\Users\UserName\[Install folder]\anaconda\Scripts\conda.exe" init powershell

#### 3. Running modules
- The parameter '-m' is necessary.
```bash
python -m scripts.game
```

#### 4. Python Grammer
- Sequence Unpacking
- It means to seperate an object from different variables, like a tuple.
```python
x1, x2 = x # Where x is a ndarray with 3 dimensions
```
