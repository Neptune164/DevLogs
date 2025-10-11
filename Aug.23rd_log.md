# 开发日志

## 日期
2025-08-23

## 今日目标
### Build/加载
- 搞清 VS 的增量编译 vs 重编译行为（Ctrl+Shift+B 只在有改动时产物更新）。
- 解决插件无法加载：日志指向 IUiBuilder 注入失败（requested type IUiBuilder could not be found from scopedObjects）
- 清理旧版构造函数/无效引用，改用 [PluginService] 属性注入（DalamudPluginInterface / IChatGui / IUiBuilder）
- 删 bin/obj 后重编，/xldev 中 reload 成功
- Manifest：删掉自己加的 AssemblyName，保持 Sample 模板字段。

### 中文显示问题（核心）
- 设计并完成对照实验：
｜ A：注释 PushFont(DefaultFont) + Dalamud 英文 → 浮窗中文全部变 “=”
｜ B：注释 PushFont(DefaultFont) + Dalamud 中文 → 浮窗中文正常
｜ C：恢复 PushFont(DefaultFont) + Dalamud 英文 → 仍然是 =
- 结论：浮窗是否能显示中文完全取决于 Dalamud 是否加载了 CJK 字体（随 UI 语言），插件无法自行 AddFontFromFileTTF（会崩）。
- 游戏原生聊天框永远不支持中文；插件浮窗只有在 Dalamud UI=简体中文时才能稳定显示。

### UI/提示
- 新增“首次启动提醒”弹窗（英文文案，避免乱码）：
- 将 DrawUI() 从表达式体改为常规函数体，先 WindowSystem.Draw() 再绘制弹窗。
- 弹窗修正：去掉 AlwaysAutoResize；在 BeginPopupModal 之前使用
```c#
SetNextWindowPos(vp.GetCenter(), ImGuiCond.Appearing, new(0.5f,0.5f)); // 居中
SetNextWindowSize(new(460,0), ImGuiCond.Appearing); // 控制宽度；按钮居中
```