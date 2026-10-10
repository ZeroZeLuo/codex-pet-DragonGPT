# DragonGPT · Codex 本地宠物

浅紫白 Q 版龙族少女，保留双角、尖耳、龙翼、鳞片长尾、结饰和流苏。包含 9 类动作、57 个状态帧、16 个视线方向；v2 图集为 1536×2288，单格 192×208。

![招手](pets/shuangling/previews/waving.gif)

## 换电脑安装

先安装支持自定义 v2 宠物的 Codex 桌面应用。下载本仓库 ZIP 或 Release 安装包，完整解压；在包含 `install.ps1` 的目录打开终端。

Windows PowerShell：

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\install.ps1
```

`ExecutionPolicy Bypass` 只用于这次启动的 PowerShell 进程，不修改系统的永久设置。

macOS/Linux（目标系统需有相应 Codex 桌面应用）：

```sh
sh ./install.sh
```

默认安装到当前用户的 `.codex/pets/shuangling/`；设置过 `CODEX_HOME` 时安装到其 `pets/shuangling/`。Windows 也可显式指定目录：

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\install.ps1 -CodexHome "D:\CodexData"
```

安装后刷新 Codex 的宠物列表，选择“霜绫”。若未出现，重启 Codex；安装脚本不会自动选择宠物。

重复安装相同文件会直接提示已安装。已有不同版本时，默认停止；确定更新时运行 `install.ps1 -Replace` 或 `sh install.sh --replace`，脚本会先将旧目录备份为 `shuangling.backup-时间-标识`。

Windows 安装、重复安装和备份替换流程已经在临时目录实测；macOS/Linux 脚本未在对应系统实测。安装不需要 Python、重新生成动画或连接 Pets 云端库。

## 手动安装

把 `pets/shuangling/` 中的 `pet.json` 和 `spritesheet.webp` 一起复制到目标电脑的 `${CODEX_HOME}/pets/shuangling/`；未设置该变量时使用当前用户的 `.codex/pets/shuangling/`。预览、原图和 QA 文件无需复制到安装目录。

## 包内内容

- `install.ps1`、`install.sh`：安装脚本，校验核心文件 SHA-256。
- `pets/shuangling/`：配置、图集、HTML 预览、9 类动作 GIF 和方向循环 GIF。
- `pets/shuangling/qa/`：图集、边缘、方向盲评、视觉和连续性检查报告；代表本次制作版本的检查结果。
- `source/reference.png`：提供的原始角色参考图，便于后续修改。
- `CHECKSUMS.sha256`：本包文件校验表。
- `UPLOAD-GITHUB.md`：上传与重新下载的步骤。

在浏览器打开 `pets/shuangling/preview.html` 可播放全部动画。检查报告中的原电脑绝对路径已转成相对路径；本包不包含 Codex 账户配置、登录信息或聊天记录。

## 在 GitHub 保存

建议用私有仓库 `codex-pet-shuangling` 保存展开的文件，再把 `shuangling-v1.0.0.zip` 放到 `v1.0.0` Release，方便下载固定版本。具体步骤见 [上传说明](UPLOAD-GITHUB.md)。

本包未新增素材使用许可；仓库可见性由上传者决定。
