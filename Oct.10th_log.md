## Daily Log
### Time
- 2025-10-10

### Workload
- 1. Implement Flask APIs and send responses to the frontend page
- 2. Design testing module to predict results
- 3. Create the remote repository for Syris

### Problem shooting
#### 1. About PowerShell
- PowerShell can't accept parameters like:
```bash
    rmdir /q /s <dir>
```
- Instead, use:
```bash
    Remove-Item -Recurse -Force <dir>
```

#### 2. Git and project structure
- When using Git, create repo inside of the aiming folder
```bash
 # don't init outside of it. Other words, not parent folder
    git init /Syris
```

#### 3. Clean step in Git
```bash
    git init
    git add .
    git commit -m 'message'
```
#### 4. About .gitignore
- It shouldn't contain any spaces. Besides, a sigal file doesn't contain slash
```
    <folder_name>/
    *.<suffix>
```
- If forget to add something in .gitignore
```bash
    git rm --cached <filename>
    git add .
    git commit -m 'message'
    git check-ignore -v <filename>
    git push origin main
```

#### 5. About creating repos on GitHub
- Do not initialize repos with .gitignore, lisence or README. If so, doing:
```bash
    git pull origin main --allow-unrelated-histories
    git push origin main
```

#### 6. About "mask" in Pandas
- A boolean filter of **True and False values**. One per row, tells pandas which rows to keep.
```python
    mask = (cleaned_data['datetime']>=start) & (cleaned_data['datetime']<end)
```
- The mask is **temporary and an intermediate** boolean array (or Series) used at the moment of filtering
- unless assigning it as a column.

#### 7. About "__init__.py"
- It usually contains nothing. An empty one is enough to mark a package.
- Tell Python: This folder isn't just a random collection of files - treat it as a module namespace

#### 8. About SSH keys
- Even though WSL holds the SSH keys, Windows still has to update SSH keys.
- The real authentication path is not Windows' native SSH keys but rather an indrect credential bridge
```bash
    ssh username@windows-ip
    # connect to Windows' built-in OpenSSH server(sshd.exe)
    # which runs in the Windows user space, not inside WSL
```

#### 9. pandas.Dataframe.iloc
- Purely integer-location based indexing for selection by position
- .loc -> by lables
- In Python (and NumPy/Pandas), negative indices count from the end of a sequence

| index | description |
|-------|-------------|
| 0 | first element |
| 1 | second element |
| -1 | last element |
| -2 | second to last element | 

#### 10. About branches in Git
```bash
    git log # check the log, remember to add messages when comitting
    git checkout <hash_code> # local IDE shows old version
    ####### If not in any branch -> "You're in 'detached HEAD' state" ########
    git checkout main # return current version
    git branch <branch_name> || git checkout <branch_name>
    git checkout -b <branch_name> # all-in-one
    git status || git branch # check branches status
    git checkout main || git merge <branch_name> # timeline synchronization
```

#### 11. About flask.jsonify()
- Serialize the given arguments as JSON and return a response object with the application/json mimetype
- **a full HTTP-compliant JSON response**

#### 12. Set remote repo
```bash
    git remote add origin https://github.com/<username>/<project>.git
    git remote -v # check that it worked
    git branch -M main
    git push origin main
```