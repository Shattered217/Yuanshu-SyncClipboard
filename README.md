# 元书输入法 同步剪切板方案

在元书输入法中通过脚本功能对接 [SyncClipboard](https://github.com/Jeric-X/SyncClipboard) 项目同步文本剪贴板。

## 文件

- `yuanshu-sync.js`：脚本源文件。
- `import_syncclipboard.yaml`：元书脚本导入文件，脚本名称为「共享剪贴板」。
- `import_toolbar_syncclipboard.yaml`：两个工具栏项：「剪贴板」和「共享剪贴板」。

## 安装

1. 开启元书 Pro、键盘完全访问。
2. 在「脚本」页面导入 `import_syncclipboard.yaml`。
3. 在「脚本 → … → 变量」中添加以下变量，名称不要带 `$`：

   | 变量名                  | 内容                                                                  |
   | ----------------------- | --------------------------------------------------------------------- |
   | `syncClipboardUrl`      | SyncClipboard 的 HTTPS 地址，例如 `https://syncclipboard.example.com` |
   | `syncClipboardUser`     | SyncClipboard 用户名                                                  |
   | `syncClipboardPassword` | SyncClipboard 密码                                                    |

4. 在「工具栏项」页面导入 `import_toolbar_syncclipboard.yaml`。

不要修改脚本名称；工具栏通过「共享剪贴板」这个名称调用脚本。

## 同步规则

- 手机剪贴板与服务器相同：不操作。
- 手机内容未出现在服务器历史记录中：上传手机内容。
- 手机内容已在服务器历史记录中：下载服务器当前内容。

仅支持文本，并且每次都需要手动点击「共享剪贴板」。如果手机保留的是以前同步过的旧文本，脚本会将服务器当前内容下载到手机。
