# Wallhaven 壁纸自动更换程序

一个适用于 Windows 的壁纸自动更换工具，支持托盘菜单、定时/手动切换、参数配置、自动清理旧壁纸。基于 Wallhaven API，开源友好。

## 功能特性
- 托盘图标与右键菜单
- 定时自动切换壁纸
- 手动一键切换壁纸
- 配置参数一键编辑
- 自动清理过期壁纸(天）
- 支持自定义 API Key、分辨率、分类等

## 依赖环境
- Python 3.7+
- requests
- pystray
- Pillow
- tkinter（标准库自带）

## 安装依赖
```shell
pip install -r requirements.txt
```
或手动安装：
```shell
pip install requests pystray pillow
```

## 使用方法
1. 克隆或下载本项目。
2. 运行 `wallhaven_wallpaper.py`：
   ```shell
   python wallhaven_wallpaper.py
   ```
3. 首次运行会自动生成 `config.json` 配置文件和 `tmp` 文件夹。
4. 托盘菜单可进行壁纸切换、定时开关、参数配置、退出等操作。

## 配置说明（config.json）
- `api_url`：Wallhaven API 地址，默认无需修改。
- `api_key`：可选，填写你的 Wallhaven API Key 可获取更多内容。
- `params`：API 查询参数，如分辨率、分类、纯净度等，参考 [https://wallhaven.cc/help/api](https://wallhaven.cc/help/api)。
- `interval_minutes`：定时切换间隔（分钟）。

## 打包为 EXE（可选）
需先安装 pyinstaller：
```shell
pip install pyinstaller
```
然后执行：
```shell
pyinstaller wallhaven_wallpaper.spec
```

## Windows 11 开机自启设置

如需让本程序随 Windows 11 开机自启，可按以下方法操作：

1. 打包为 EXE（推荐，见上文打包说明），假设生成的路径为 `C:\D\cmds\wallhaven-wallpaper\dist\wallhaven_wallpaper.exe`
2. 按下 `Win + R`，输入 `shell:startup` 并回车，打开“启动”文件夹。
3. 将 `wallhaven_wallpaper.exe` 的快捷方式复制到该文件夹内。
4. 重启电脑后，程序会自动随 Windows 启动。

> 如需取消自启，删除“启动”文件夹中的快捷方式即可。

## 常见问题
- 若壁纸未切换，请检查网络、API Key、参数设置。
- 若托盘图标不显示，请确保已安装 pystray、Pillow。
- 日志输出在 `wallpaper.log`，可用于排查问题。
