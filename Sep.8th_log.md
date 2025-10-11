# 开发日志
## 时间
- 2025-09-08

## 解决问题
####  1. 获取Syracuse 2023-1-24 到 2025-09-08的天气数据
- 网站已收藏，每天只能获取1000条，大概需要近五年的csv数据

####  2. 通过ssh和scp将csv数据传输到Windows端
```bash
scp *.csv sirius@IPAddress:~ # 放到默认的目录
ssh sirius@IPAddress
powershell
mv *.csv Target_Address # 注意切powershell
```
#####  3. 使用VS Code的Remote SSH插件连接目标主机后，如果更新Python包，记得restart解释器
```bash
command + shift + P: Restart Python Language
```
####  4. Python列表推导式（类Lambda）
```python
[表达式 for 变量 in 可迭代对象 if 条件]
例子：
A = [1,2,3,4,5]
B = [1,2,3]
A = [x for x in A if x not in B]
```
####  5. （ADB与Android Developing相关）开启顺序
- Win端Emulator - Mac端ssh -L 5037:127.0.0.1:5037 sirius@IPAddress - Mac端Android Studio

#### 6. to_csv()
- 第一个参数是存储路径，使用拼接时为了避免斜杠出错，最好使用：
```python
import os
data.to_csv(os.path.join(target_path + ".\data\file_name_csv"))
```