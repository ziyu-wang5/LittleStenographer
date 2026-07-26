# Little Stenographer / 小小速记员

> A fast, local-first voice typing tool for Windows.  
> 一款面向 Windows 的快速、本地优先语音输入工具。

Little Stenographer turns speech into text and inserts it at the current cursor position. It is designed for short notes, chat messages, prompts, and everyday writing without sending audio to a cloud service.

Little Stenographer 将语音转换为文本，并自动填入当前光标位置。它适合记录想法、撰写聊天消息、输入 AI 提示词和日常文字输入；音频识别默认在本机完成。

## Highlights / 主要特点

- **Local speech recognition / 本地语音识别** — Uses the bundled SenseVoiceSmall engine; no cloud API key is required for normal use.  
  使用内置的 SenseVoiceSmall 引擎，正常使用不需要云端 API Key。
- **Press and hold to dictate / 按住即说** — Hold `Alt + Space` to record and release it to recognize and paste the result.  
  按住 `Alt + Space` 开始录音，松开后自动识别并粘贴结果。
- **Fast feedback / 快速反馈** — A compact floating indicator distinguishes listening from recognition, so the working state is always clear.  
  通过悬浮状态提示区分“正在聆听”和“正在识别”，减少等待时的不确定感。
- **Cursor insertion and clipboard fallback / 自动填入与剪贴板兜底** — The result is pasted into the active application; if direct paste is unavailable, it is copied to the clipboard.  
  结果优先粘贴至当前应用的光标位置；如粘贴不可用，会自动复制到剪贴板。
- **Tray-first desktop app / 托盘优先** — After startup the app stays in the system tray. Click the tray icon to open the main window, history, settings, and recording-file retest tool.  
  启动后自动驻留系统托盘。点击托盘图标可打开主窗口、查看历史、调整设置或选择录音文件复测。
- **Chinese and English / 中英文支持** — Automatic language detection is enabled by default, with Chinese-first and English-first options available.  
  默认自动识别中英文，也可选择“中文优先”或“English first”。

## Download and install / 下载与安装

1. Open the [Releases](../../releases) page.
2. Download `Little Stenographer_*_x64-setup.exe` from the latest release assets.
3. Run the installer, then launch **Little Stenographer** from the Start menu.

1. 打开 [Releases](../../releases) 页面。
2. 在最新版本的 Assets 中下载 `Little Stenographer_*_x64-setup.exe`。
3. 运行安装程序，然后从开始菜单启动 **Little Stenographer**。

The release installer includes the local SenseVoiceSmall model. No separate model download is required for normal use.

正式安装包已包含 SenseVoiceSmall 本地模型，普通使用无需额外下载模型。

## How to use / 使用方法

1. Start the app and wait until the main window shows **“本地引擎就绪 / Local engine ready”**.
2. Place the text cursor in any target application, such as a browser, editor, chat app, or AI input box.
3. Hold `Alt + Space`, then begin speaking after the listening indicator appears.
4. Release `Alt + Space`. The floating indicator changes to recognition, and the text is inserted when recognition finishes.

1. 启动应用，等待主窗口显示 **“本地引擎就绪”**。
2. 将光标放到浏览器、编辑器、聊天软件或 AI 输入框等目标应用中。
3. 按住 `Alt + Space`；看到“正在聆听”提示后开始说话。
4. 松开 `Alt + Space`。悬浮提示会转为识别状态，完成后文本会自动填入当前光标位置。

### Tips / 使用建议

- Speak naturally, but pause briefly between long paragraphs or separate list items for clearer results.  
  长段表达或分点表达之间稍作停顿，通常能获得更清晰的结果。
- Use the main window’s **“选择录音文件复测 / Retest with a recording file”** button to compare results without recording again.  
  可通过主窗口的 **“选择录音文件复测”** 重复测试已有录音，无需反复朗读。
- The global hotkey can be changed in the main window.  
  可在主窗口中修改全局快捷键。

## Privacy / 隐私

Speech recognition is performed locally by default. Audio, transcription history, and settings remain on the local device unless you deliberately export or share them.

默认情况下，语音识别在本机完成。音频、识别历史和设置均保留在本地设备，除非你主动导出或分享。

## Building from source / 从源码构建

### Requirements / 环境要求

- Windows 10 or later, 64-bit / Windows 10 或更高版本，64 位
- Node.js and npm / Node.js 与 npm
- Rust stable toolchain and Microsoft C++ Build Tools / Rust stable 工具链与 Microsoft C++ Build Tools

### Development / 开发运行

```powershell
npm install
npm run tauri:dev
```

### Production build / 生成安装包

```powershell
npm run tauri -- build
```

The minimal source archive does not include model weights. Before building it, follow [MODEL_SETUP.md](MODEL_SETUP.md) to place the required SenseVoiceSmall model files in `src-tauri/resources/models/sensevoice/`.

最小源码包不包含模型权重。构建前请阅读 [MODEL_SETUP.md](MODEL_SETUP.md)，并将所需的 SenseVoiceSmall 模型文件放入 `src-tauri/resources/models/sensevoice/`。

## License / 许可证

The project’s original source code is available under the [MIT License](LICENSE). Third-party software and model weights have their own licenses and usage conditions; see [LICENSES/THIRD_PARTY_NOTICES.md](LICENSES/THIRD_PARTY_NOTICES.md). The SenseVoice model license is also included with the installed model files.

本项目新增源码采用 [MIT License](LICENSE)。第三方软件与模型权重分别受其原始许可证及使用条件约束，详见 [LICENSES/THIRD_PARTY_NOTICES.md](LICENSES/THIRD_PARTY_NOTICES.md)。SenseVoice 模型许可证也会随安装包中的模型文件一同提供。
