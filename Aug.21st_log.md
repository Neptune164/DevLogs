# 开发日志

## 日期
2025-08-21

## 今日目标
- [x] 首次利用Dalamud DLL文件进行热加载（Hot Reload）
- [x] 调试Sample Plugin功能接口  

## 开发内容
### 模块/功能点
- **名称**: Sample Plugin
- **描述**: Dalamud官方提供的插件模板，主要实现了在游戏中用以下命令可唤出插件页面的功能
```C# 
/pmycommand // 可在代码中修改指令
```

### 遇到的问题
1. 问题现象：VS 2022找不到SamplePlugin.sln解决方案
- 初步推测：利用Git命令clone文件前已创建VS 2022项目并且项目中存在.sln解决方案 

2. 问题现象：使用Build命令重新生成DLL文件后，游戏内并没有展示修改部分
- 初步推测：可能是DLL文件没有被载入到最新版本

### 调试与解决
#### 问题1
- 尝试方案1：重新clone repository → 结果：失败   
- 尝试方案2：删除原本创建的项目，在powershell中使用git clone + url命令 → [x] 成功

#### 问题2
- 尝试方案：Dalamud重新载入完整DLL文件地址，确保加载最新版本的DLL → [x] 成功

### 关键代码片段
```C#
/// 示例代码
ImGui.TestUniformatted("Plugin version: v0.0.1"); // 使用版本号作为修改的标准，时刻关注DLL文件的修改时间
```