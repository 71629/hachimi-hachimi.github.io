# 使用说明

## 兼容性

请在安装前检查游戏版本的兼容性。

### Windows
| 版本 | 是否支持 |
| --- | :---: |
| 日语版 | ✅ |
| 韩语版 | ⚠️ |

### Android

| 版本 | 普通安装 | 直接安装 |
| --- | :---: | :---: |
| 日语版 | ✅ | ✅ |
| 韩语版 | ⚠️ | ⚠️ |
| 繁体中文Google Play版 | ⚠️ | ❔ |
| 繁体中文Mycard版 | ⚠️ | ⚠️ |
- ✅ - 完全支持。
- ⚠️ - 可以使用，但游戏可能因为外部环境因素导致无法正常运行（例如反作弊）。
- ❔ - 也许能运行，但是不要抱有太大期望。
- ❌ - 不支持。


## 安装

### Windows

从v0.13.0版本开始，Hachimi目前支持两种不同的安装方法。 **请注意：只能使用一种安装方法，使用安装程序或手动安装，切勿同时使用两种安装方法。**

#### 方法1：DotLocal DLL redirection（.local文件DLL重定向） （UnityPlayer.dll）（推荐使用）

::: 注意事项
部分反作弊系统（如Vanguard）对系统内启用的DLL重定向机制采取严苛监控策略，即便该操作不会直接影响其所保护的游戏运行。建议在游玩采用Vanguard等同类反作弊系统的游戏时，务必提前禁用DLL重定向功能。
:::

::: 说明
游戏在安装完成后无法运行？请定位到游戏的安装路径，右键游戏的exe文件，打开属性，转到兼容性选项卡，并打开**禁用全屏优化**。
:::

- **使用安装程序** 从[发布页面](https://github.com/Hachimi-Hachimi/Hachimi/releases)下载最新的`hachimi_installer.exe`，打开它，**在Target一栏选择UnityPlayer.dll**并点击Install。

首次安装时，安装程序可能会向你询问是否开启DotLocal DLL redirection。点击OK，它就会为你启用此功能。**启用后，你必须重新启动你的计算机。**

- **手动安装**
1. 请参阅[这篇文章](https://learn.microsoft.com/zh-cn/windows/win32/dlls/dynamic-link-library-redirection#optional-configure-the-registry)中的“配置注册表”部分去开启DLL重定向，并在完成后重新启动你的计算机。
2. 从[发布页面](https://github.com/Hachimi-Hachimi/Hachimi/releases)下载最新的`hachimi.dll`。
3. 在游戏的安装路径新建一个名为`umamusume.exe.local`的文件夹，将下载好的DLL移动到这里，并将其命名为`UnityPlayer.dll`。
4. 从[Cellar发布页面](https://github.com/Hachimi-Hachimi/Cellar/releases)下载最新的`cellar.dll`。
5. 将其移动至`umamusume.exe.local`并命名为`apphelp.dll`.

::: 说明
给想玩英雄联盟（LoL）以及无畏契约（Valorant）的玩家的一些提示：当你每次想玩这些游戏时，你都要禁用DLL重定向。你可以使用这个程序去快速启用/禁用它：https://github.com/LeadRDRK/DotLocalToggle/releases 运行它，直到它显示已禁用DLL重定向，然后重新启动计算机。
:::

#### 方法2：Plugin shimming（插件兼容适配）（cri_mana_vpx.dll）

::: warning
此方法在最近单子更新以后不再有效，请按照下面的指引迁移到方法1。
:::

#### 从方法2迁移到方法1
您可能需要从方法2切换至方法1，但此过程相比反向操作（方法1到方法2只需卸载后重装）更为复杂。

首先需要彻底卸载Shinmy，删除时请确保其未在后台运行，因为它会在DMM关闭后存活最多30秒，并可能自我恢复。**最简单的方法是直接使用安装程序**（该程序同时支持卸载功能），它会自动为您清理所有残留文件。  

完成上述操作后，即可正常卸载Hachimi。

### Android

最简单的方法是使用[UmaPatcher](https://github.com/LeadRDRK/UmaPatcher)，它会自动帮你修改apk文件，建议在使用此功能前，确保未提前安装原版游戏。

::: 危险
若您已安装原版游戏，首次安装修改版前必须将其卸载。后续更新时，可直接安装新版修改版而无需卸载。
:::

::: 危险
请不要从APKPure下载你的apk，这样会导致一些问题。
:::

1. 从[发布页面](https://github.com/LeadRDRK/UmaPatcher/releases)下载最新的UmaPatcher。
2. 准备一个游戏的安装包，可以是以下几种：
    - **Split APK files（拆分APK文件）:** 一个基础APK文件和其中一个拆分配置APK（config.arm64_v8a，config.armeabi-v7a等),
    请仅选择适合您设备的拆分配置。
    此功能目前仅限日语版使用。
    - **单一APK文件**: 一个完整的，未拆分的APK文件。
    - **XAPK文件**: 一个包含拆分后的APK文件的ZIP压缩包（将扩展名重命名为了.xapk）。
3. 运行UmaPatcher并选择“Normal Install”，并选择你已经准备好的游戏安装包。
4. 点击“Patch”按钮即可开始进行安装流程。

注意：应用更新后需从第二步开始重新执行安装流程。

#### 对于已经root的用户
UmaPatcher包含root安装选项，无需卸载游戏即可使用，且游戏仍可通过任意应用商店正常更新。

游戏安装后，点击主页上方的卡片选择你要安装的游戏（如果需要的话）。然后选择“Direct install”并点击“Patch”即可。不需要任何额外的文件。

注意：应用更新后需重新执行安装流程。

#### 手动安装
1. 自行构建或从[发布页面](https://github.com/Hachimi-Hachimi/Hachimi/releases)下载预编译库文件。
2. 提取游戏的APK文件，你也行会用得上[apktool](https://apktool.org/)这个软件。
3. 将`lib`文件夹内的所有文件夹里的`libmain.so`重命名为`libmain_orig.so`。
4. 将代理库文件复制至对应架构文件夹（例如：`libmain-arm64-v8a.so` 应放入 `lib/arm64-v8a`），并将其重命名为 `libmain.so`。
5. 构建APK文件并安装

## First Time Setup
成功安装Hachimi后，初次启动游戏将显示如下对话框：

![First Time Setup](/assets/first-time-setup.jpg)

*如果没有显示对话框代表Hachimi没有被正确安装，请检查你的安装步骤并重试。*

点击“Next”，选择您所需的翻译仓库，随后点击“Done”保存配置并启动更新检查。

Hachimi将提示您下载新翻译更新，点击“Yes”即可开始下载翻译文件。