# 开发日志
## 时间
- 2025-09-09

## 解决问题
#### 1. push到远程仓库前先写“.gitignore”编辑掉不需要push的文件夹或文件
#### 2. 有关于Dataframe使用to_csv()等函数
- 因为Dataframe是储存在内存中的，如果中途需要转成中间数据储存方便纠错，一定要注意一些categorical类型和date类型的变量类型，可能会全都变成object类型
#### 3. f-string，在字符串内引用变量
```python
name = "Name"
filename = f"{name}_filePath.csv"
```
#### 4. Date类型在Polars中
```python
# 截断to_datetime()后会存在的秒级
cleaned_data = cleaned_data.with_columns(pl.col("datetime").str.to_datetime().cast(pl.Date))
```