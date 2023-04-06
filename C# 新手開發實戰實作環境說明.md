# C# 新手開發實戰 實作環境說明

為了能讓大家能在課堂上順利地進行實作，請大家務必在上課前把需要的軟體全部安裝好，以下是安裝的相關軟體與安裝步驟與說明，如果安裝過程有遇到任何問題，請上本班專屬 Facebook 社團提問。

## [ 上課教材 ]

本課程採用 [C# 最強入門邁向頂尖高手之路](https://www.books.com.tw/products/0010949183) 書籍，上課前請先購買並閱讀此書。

## [ 作業系統 ]

.NET 6 支援的作業系統版本，請務必確認可執行版本：

- [Install .NET on Windows](https://docs.microsoft.com/en-us/dotnet/core/install/windows?tabs=net50&pivots=os-windows&WT.mc_id=DT-MVP-4015686)
- [Install .NET on macOS](https://docs.microsoft.com/en-us/dotnet/core/install/macos?WT.mc_id=DT-MVP-4015686)
- [Install .NET on Linux](https://docs.microsoft.com/en-us/dotnet/core/install/linux?WT.mc_id=DT-MVP-4015686)

## [ 瀏覽器 ]

- [Google Chrome](http://www.google.com/intl/zh-TW/chrome/)
  - 請更新到最新版本

## [ 開發工具 ]

- Windows
  - [.NET 6.0 SDK](https://dot.net/download) (基本上不用特別安裝，因為安裝 VS2022 就會自動安裝 .NET SDK 到最新版)
  - [Visual Studio Code](https://aka.ms/vscode)
  - [Visual Studio 2022](https://aka.ms/vs2022/) (注意: **Visual Studio 2019 不支援 .NET 6.0 開發**)
    - 請安裝以下工作負載：
      - ASP.NET 與網頁程式開發 (*ASP.NET and web development*)
      - .NET 桌面開發 (*.NET Desktop Development*)

- macOS
  - [.NET 6.0 SDK](https://dotnet.microsoft.com/download/dotnet/6.0)
  - [Visual Studio Code](https://code.visualstudio.com/)
  - [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/) (非必要)

- Linux
  - [.NET 6.0 SDK](https://dotnet.microsoft.com/download/dotnet/6.0)
  - [Visual Studio Code](https://code.visualstudio.com/)

## [ GitHub Copilot ]

由於 GitHub Copilot 是一套付費的 AI 程式開發助理服務，每月 $10 美金，但有前 60 天免費試用的期間，時間到才會開始扣款，期間可以隨時取消服務。

> [About billing for GitHub Copilot](https://docs.github.com/en/copilot/overview-of-github-copilot/about-github-copilot-for-individuals#about-billing-for-github-copilot)

- Visual Studio Code

    請安裝 [GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot) 與 [GitHub Copilot Labs](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot-labs) 這兩個擴充套件。

- Visual Studio 2022

    請安裝 [GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilotvs) 擴充套件。

    [GitHub Copilot in Visual Studio 2022](https://devblogs.microsoft.com/visualstudio/github-copilot-in-visual-studio-2022/?WT.mc_id=DT-MVP-4015686)

    [Getting started with GitHub Copilot](https://docs.github.com/en/copilot/getting-started-with-github-copilot?tool=visualstudio)

## [ 測試工具 ]

- [Postman](https://www.postman.com/downloads/) | The Collaboration Platform for API Development

## [ 資料庫系統 ]

- Windows

    請安裝 [SQL Server 2019 Express Edition](https://www.microsoft.com/zh-TW/download/details.aspx?id=101064) 與 [SQL Server Management Studio](https://learn.microsoft.com/zh-tw/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver16&WT.mc_id=DT-MVP-4015686) 工具

- macOS

    使用 macOS 的學員請先安裝 [Docker Desktop on Mac](https://docs.docker.com/desktop/install/mac-install/) 並下載 [SQL Server 2019 的 Docker 容器映像](https://hub.docker.com/_/microsoft-mssql-server)

    ```sh
    sudo docker pull mcr.microsoft.com/mssql/server:2019-latest
    ```

    建議閱讀 [Quickstart: Run SQL Server container images with Docker](https://docs.microsoft.com/en-us/sql/linux/quickstart-install-connect-docker?view=sql-server-ver15&pivots=cs1-bash&WT.mc_id=DT-MVP-4015686) 官網文件。

    > 推薦文章：[使用 Docker 執行 SQL Server on Linux 容器之常用工具與命令](https://blog.miniasp.com/post/2020/08/04/Docker-SQL-Server-on-Linux)

## [ 部署環境 ]

- Windows 10 部署環境

  - 請以系統管理員身份執行用 Windows PowerShell 執行以下命令以安裝 IIS 角色服務

      ```ps1
      Get-WindowsOptionalFeature -Online

      Enable-WindowsOptionalFeature -Online -FeatureName IIS-WebServerRole,IIS-IPSecurity,IIS-HttpCompressionDynamic,IIS-ApplicationInit
      ```

  - 請在安裝完 IIS 之後，下載 [.NET 6.0 SDK](https://dotnet.microsoft.com/download/dotnet/6.0) 頁面中最新版 ASP․NET Core Runtime 的 **Hosting Bundle** 安裝檔。

    > 請注意：你一定要在安裝 IIS 之後才能執行 **Hosting Bundle** 安裝程式。

- Windows Server 部署環境 (2016/2019)

  - 請以系統管理員身份執行用 Windows PowerShell 執行以下命令以安裝 IIS 角色服務

      ```ps1
      Get-WindowsFeature | Format-Table -Wrap
      Install-WindowsFeature Web-WebServer,Web-IP-Security,Web-Dyn-Compression,Web-AppInit
      ```

  - 請在安裝完 IIS 之後，下載 [.NET 6.0 SDK](https://dotnet.microsoft.com/download/dotnet/6.0) 頁面中最新版 ASP․NET Core Runtime 的 **Hosting Bundle** 安裝檔。

    > 請注意：你一定要在安裝 IIS 之後才能執行 **Hosting Bundle** 安裝程序。

- Linux 部署環境

  - 如果你上課用筆電的作業系統是 Windows 10 Version 1909 以前版本，建議可以安裝 WSL 執行環境。請參考 [介紹好用工具：WSL (Windows Subsystem for Linux)](https://blog.miniasp.com/post/2019/02/01/Useful-tool-WSL-Windows-Subsystem-for-Linux) 文章說明。

  - 如果你上課用筆電的作業系統是 Windows 10 Version 2004 以上版本，建議可以安裝 WSL 2 執行環境。請參考 [使用 WSL 2 打造優質的多重 Linux 開發環境](https://blog.miniasp.com/post/2020/07/26/Multiple-Linux-Dev-Environment-build-on-WSL-2) 文章說明。

  - 如果你上課用筆電的作業系統是 macOS 10.13 以後的版本，請安裝 [Docker Desktop on Mac](https://docs.docker.com/docker-for-mac/install/) 軟體，部署的環境可以直接在 Linux 容器中練習。

- Docker 部署環境

  - 如果你的作業系統是 Windows 10 Build 16299 以後的版本，請安裝 [Docker Desktop on Windows](https://docs.docker.com/docker-for-windows/install/)

    > Requires Microsoft Windows 10 **Professional** or **Enterprise** **64-bit**, or **Windows 10 Home 64-bit** with **WSL 2**

  - 如果你的作業系統是 macOS 10.13 以後的版本，請安裝 [Docker Desktop on Mac](https://docs.docker.com/docker-for-mac/install/)

## [ 常用工具與擴充套件 ]

- 安裝 .NET 全域工具 (Global Tool)

  - 安裝 [dotnet-ef](https://www.nuget.org/packages/dotnet-ef) 工具

    ```sh
    dotnet tool update --global dotnet-ef
    ```

    > [EF Core tools reference (.NET CLI) - EF Core](https://docs.microsoft.com/en-us/ef/core/cli/dotnet?WT.mc_id=DT-MVP-4015686)

  - 安裝 [dotnet-sql-cache](https://www.nuget.org/packages/dotnet-sql-cache) 工具

    ```sh
    dotnet tool update --global dotnet-sql-cache
    ```

    > [Distributed caching in ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/performance/caching/distributed?view=aspnetcore-6.0)

  - 安裝 [dotnet-aspnet-codegenerator](https://www.nuget.org/packages/dotnet-aspnet-codegenerator) 工具

    ```sh
    dotnet tool update -g dotnet-aspnet-codegenerator
    ```

    > [dotnet/Scaffolding: Code generators to speed up development.](https://github.com/dotnet/Scaffolding)

  - 安裝 [EntityFrameworkCore.Generator](https://www.nuget.org/packages/EntityFrameworkCore.Generator) 工具

    ```sh
    dotnet tool update -g EntityFrameworkCore.Generator
    ```

    > [loresoft/EntityFrameworkCore.Generator: Generator Entity Framework Core source code models](https://github.com/loresoft/EntityFrameworkCore.Generator)

  - 安裝 [Microsoft.Web.LibraryManager.Cli](https://www.nuget.org/packages/Microsoft.Web.LibraryManager.CLI) 工具

    ```sh
    dotnet tool update -g Microsoft.Web.LibraryManager.CLI
    ```

    建議觀看 [Use the LibMan CLI with ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/client-side/libman/libman-cli?view=aspnetcore-5.0) 官網文件。

    > [Using LibMan](https://github.com/aspnet/LibraryManager/wiki/Using-LibMan-CLI)

  - 安裝 [Microsoft.dotnet-openapi](https://www.nuget.org/packages/Microsoft.dotnet-openapi)  工具

    ```sh
    dotnet tool update -g Microsoft.dotnet-openapi
    ```

    建議觀看 [使用 OpenAPI 工具開發 ASP.NET Core 應用程式](https://docs.microsoft.com/zh-tw/aspnet/core/web-api/microsoft.dotnet-openapi?view=aspnetcore-5.0) 官網文件。

  - 安裝 [dotnet-search](https://www.nuget.org/packages/dotnet-search) 工具

    ```sh
    dotnet tool update --global dotnet-search
    ```

    > [billpratt/dotnet-search: Search for Nuget packages using the .NET Core CLI.](https://github.com/billpratt/dotnet-search)

  - 安裝 [dotnet-t4](https://www.nuget.org/packages/dotnet-t4/) 或 [dotnet-t4-project-tool](https://www.nuget.org/packages/dotnet-t4-project-tool) 工具

    ```sh
    dotnet tool update -g dotnet-t4
    ```

    如果想要跟「專案」中的套件一起安裝此工具，可以改用以下命令：

    ```sh
    dotnet add package dotnet-t4-project-tool
    ```

    > [mono/t4: T4 text templating engine](https://github.com/mono/t4)

  - 安裝 [dotnet-format](https://www.nuget.org/packages/dotnet-format) 工具

    > 此工具已經內建於 .NET 6 SDK 之中，不需要額外安裝，詳見 [dotnet/format: Home for the dotnet-format command](https://github.com/dotnet/format)！

  - 安裝 [dotnet-serve](https://www.nuget.org/packages/dotnet-serve) 工具

    ```sh
    dotnet tool update --global dotnet-serve
    ```

    > [natemcmaster/dotnet-serve: Simple command-line HTTPS server for the .NET Core CLI](https://github.com/natemcmaster/dotnet-serve)

  - 安裝 [dotnet-ignore](https://www.nuget.org/packages/dotnet-ignore) 工具

    ```sh
    dotnet tool update -g dotnet-ignore
    ```

    > [Arasz/dotnet-ignore: .NET CLI tool that can download .gitignore file from gitignore repository](https://github.com/Arasz/dotnet-ignore)

  - 安裝 [try-convert](https://www.nuget.org/packages/try-convert) 工具

    ```sh
    dotnet tool update -g try-convert
    ```

    > [dotnet/try-convert: Helping .NET developers port their projects to .NET Core!](https://github.com/dotnet/try-convert)

  - 安裝 [upgrade-assistant](https://www.nuget.org/packages/upgrade-assistant) 工具

    ```sh
    dotnet tool update -g upgrade-assistant
    ```

    > [.NET Upgrade Assistant 總覽](https://docs.microsoft.com/zh-tw/dotnet/core/porting/upgrade-assistant-overview?WT.mc_id=DT-MVP-4015686)

  - 安裝 [NSwag.ConsoleCore](https://www.nuget.org/packages/NSwag.ConsoleCore) 工具

    ```sh
    dotnet tool update -g NSwag.ConsoleCore
    ```

    > [NSwag: The Swagger/OpenAPI toolchain for .NET, ASP.NET Core and TypeScript](https://github.com/RicoSuter/NSwag)

  - 如果要更新已安裝過的專案範本，請輸入以下命令：

    ```sh
    dotnet new --update-check
    dotnet new --update-apply
    ```

  - 更新 **.NET Global Tool** 到相容於目前 .NET SDK 的版本

    使用 `dotnet tool update` 也可以用於「安裝」用途，因此也可以直接使用這個命令批次安裝！

    ```sh
    dotnet tool update --global dotnet-ef
    dotnet tool update --global dotnet-sql-cache
    dotnet tool update --global Microsoft.dotnet-openapi
    dotnet tool update --global dotnet-aspnet-codegenerator
    ```

    > 注意：如果要安裝微軟官方提供的 .NET Global Tool 全域工具，有些工具會跟目前 .NET Runtime 有相依性，因此若不特別加上 `--version` 參數來指定版本的話，預設就會安裝最新穩定版，也意味著你的 .NET SDK 也要升級到最新穩定版才能正常執行。

    ```sh
    dotnet tool update --global EntityFrameworkCore.Generator
    dotnet tool update --global Microsoft.Web.LibraryManager.CLI
    dotnet tool update --global dotnet-search
    dotnet tool update --global dotnet-t4
    dotnet tool update --global dotnet-serve
    dotnet tool update --global dotnet-ignore
    dotnet tool update --global try-convert
    dotnet tool update --global upgrade-assistant
    dotnet tool update --global NSwag.ConsoleCore
    ```

  - 列出目前所有安裝過的 **.NET Global Tool**

    ```sh
    dotnet tool list -g
    ```

  - 移除本課程安裝的 **.NET Global Tool** (未來如果有不需要用到的工具可以自行移除)

    ```sh
    dotnet tool uninstall -g dotnet-ef
    dotnet tool uninstall -g dotnet-sql-cache
    dotnet tool uninstall -g Microsoft.dotnet-openapi
    dotnet tool uninstall -g dotnet-aspnet-codegenerator
    dotnet tool uninstall -g EntityFrameworkCore.Generator
    dotnet tool uninstall -g Microsoft.Web.LibraryManager.CLI
    dotnet tool uninstall -g dotnet-search
    dotnet tool uninstall -g dotnet-t4
    dotnet tool uninstall -g dotnet-serve
    dotnet tool uninstall -g dotnet-ignore
    dotnet tool uninstall -g try-convert
    dotnet tool uninstall -g upgrade-assistant
    dotnet tool uninstall -g NSwag.ConsoleCore
    ```

- 將 .NET CLI 內建的開發用憑證設為受信任的根憑證

    ```sh
    dotnet dev-certs https --trust
    ```

    想要測試開發用憑證已經受信任，可以輸入以下命令，並開啟瀏覽器測試是否有出現連線警告：

    ```sh
    dotnet serve --tls
    ```

    請注意：開發用憑證有效期僅一年，一年之後必須用以下命令，先清空憑證，然後再產生一組新的憑證，並設為受信任的根憑證：

    ```sh
    dotnet dev-certs https --clean
    dotnet dev-certs https --trust
    ```

- Visual Studio Code

  - 安裝 [.NET Core Extension Pack](https://marketplace.visualstudio.com/items?itemName=doggy8088.netcore-extension-pack) 擴充套件

    ```sh
    code --install-extension doggy8088.netcore-extension-pack
    ```

  - 安裝 [SQL Server (mssql)](https://marketplace.visualstudio.com/items?itemName=ms-mssql.mssql) 擴充套件

    ```sh
    code --install-extension ms-mssql.mssql
    ```

  - 安裝 [Docker](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker) 擴充套件

    ```sh
    code --install-extension ms-azuretools.vscode-docker
    ```

- Visual Studio 2022 (17.5.0+)

    > 建議直接升級到 Visual Studio 2022 目前最新版本，你可以到[這裡](https://docs.microsoft.com/zh-tw/visualstudio/releases/2022/release-notes)下載最新版，或是直接從 Visual Studio 2022 的 **[說明]/[查看是否有更新]**。

  - 建議安裝
    - [Open in Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.OpeninVisualStudioCode)
      - 快速從 Visual Studio 2022 裡面直接開啟 Visual Studio Code 工具並自動開啟目前專案資料夾！
    - [EF Core Power Tools](https://marketplace.visualstudio.com/items?itemName=ErikEJ.EFCorePowerTools)
      - 提供 EF Core 資料庫反向工程工具、自動資料庫移轉、產生資料庫圖表等功能
    - [Bundler & Minifier 2022+](https://marketplace.visualstudio.com/items?itemName=Failwyn.BundlerMinifier64)
      - 替 ASP.NET Core 網站加入 Bundling (多檔打包) 與 Minification (最小化) 功能
    - [REST Client](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.RestClient)
      - 在 Visual Studio 2022 測試 HTTP / REST API 的好工具
    - [Productivity Power Tools 2022](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.ProductivityPowerPack2022)
    - [Productivity Power Tools Options Page 2022](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.ProductivityPowerToolsOptionsPage2022)
    - [SQLite/SQL Server Compact Toolbox](https://marketplace.visualstudio.com/items?itemName=ErikEJ.SQLServerCompactSQLiteToolbox)
      - 提供 SQLite/SQL Server Compact Toolbox 便利的管理工具，也可以用來移轉資料庫到不同資料庫
    - [ASP.NET MVC Snippet Pack](https://marketplace.visualstudio.com/items?itemName=vs-publisher-123005.ASPNETMVCSnippetPack)
      - 這個套件包含了幾個 ASP.NET MVC 好用的程式碼片段 (`mvcaction`, `mvcpostaction` 與 `mvcpostaction2`)
      - 支援 Visual Studio 2017, 2019, 2022 版本

## [ 驗證安裝 ]

- 確認 `.NET SDK` 版本

    ```sh
    dotnet --version
    ```

    請確認為 `6.0.407` 或 `7.0.202` 版本！

- 確認可以建立 MVC 專案範本並可透過瀏覽器開啟網站

    ```sh
    mkdir m1 && cd m1
    dotnet new mvc
    dotnet run --no-launch-profile
    ```

    > 用瀏覽器開啟 <http://localhost:5000> 網址

- 確認 `dotnet-ef` 版本資訊：

    ```sh
    dotnet ef --version
    ```

    你會得到以下結果：

    ```txt
    Entity Framework Core .NET Command-line Tools
    7.0.4
    ```

- 確認 Visual Studio Code 版本

    ```sh
    code --version
    ```

    請確認至少為 `1.77.0` 以上版本！

    請確認 [C# 擴充套件](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) 已確實安裝：

    ![已安裝 C# 擴充套件的火焰圖示](https://user-images.githubusercontent.com/88981/81782493-7444ff80-952c-11ea-9763-a6d6853a6575.png)

    參考文件：[C# 與 Visual Studio Code 使用者入門](https://docs.microsoft.com/zh-tw/dotnet/core/tutorials/with-visual-studio-code)

- 確認 Visual Studio 2022 版本 (Windows Only)

    建議直接升級到 Visual Studio 2022 目前最新版本，你可以到[這裡](https://docs.microsoft.com/zh-tw/visualstudio/releases/2022/release-notes)下載最新版。

    如果只想開發 ASP.NET Core 5.0 的話，請確認至少安裝 Visual Studio 2019 `v16.9.4` 以上版本，並且安裝必要的**工作負載**(Workload)！

    ![查看 Visual Studio 2019 版本資訊](https://user-images.githubusercontent.com/88981/81782035-c89baf80-952b-11ea-9c9d-64218285fe18.png)

- 請**務必確認**你的 Windows 10 輸入法設定 🔥🔥🔥

    請參考 [開發者必學的多語言輸入法設定技巧：使用 Windows PowerShell 快速建立](https://blog.miniasp.com/post/2020/03/19/Devs-must-setup-multi-language-input-method) 文章進行設定。

    在 Visual Studio Code 裡面有許多好用的快速鍵，當你使用 Windows 10 預設的輸入法設定，就會完全按不出這些快速鍵，例如：

  - `Ctrl + Space`

      在各種開發工具中，這個快速鍵通常用來觸發 IntelliSense 輸入建議。

      但是當系統切換到 **中文** 語言時，主要用來**啟用/停用**中文輸入法。

  - `Ctrl + ,`

      在許多應用程式的快速鍵中，這個快速鍵通常用來開啟 **設定** 視窗。

      但是當系統切換到 **中文** 語言時，無論你切換到中文或英文模式，都會輸出「**全形逗點**」。

  - `Ctrl + .`

      在各種開發工具中，這個快速鍵通常用來觸發 Code Actions 或 Quick Fixes 等程式碼重構建議。

      但是當系統切換到 **中文** 語言時，無論你切換到中文或英文模式，都會輸出「**全形句點**」。

## [ 課前學習資源 ]

- [使用 C# 邁出您的第一步 - Learn | Microsoft Docs](https://docs.microsoft.com/zh-tw/learn/paths/csharp-first-steps/)
- [C# Guide | Microsoft Docs](https://docs.microsoft.com/en-us/dotnet/csharp/) ( [中文翻譯](https://docs.microsoft.com/zh-tw/dotnet/csharp/) )
- [.NET Core Guide | Microsoft Docs](https://docs.microsoft.com/en-us/dotnet/core/index) ( [中文翻譯](https://docs.microsoft.com/zh-tw/dotnet/core/index) )
- [Samples and tutorials | Microsoft Docs](https://docs.microsoft.com/en-us/dotnet/samples-and-tutorials/) ( [中文翻譯](https://docs.microsoft.com/zh-tw/dotnet/samples-and-tutorials/) )
- [Using .NET Core in Visual Studio Code](https://code.visualstudio.com/docs/languages/dotnet)
  - [Get started with VS Code using C# and .NET Core on Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-Csharp-NET-Core-Windows)
  - [Get started with VS Code using C# and .NET Core on Mac](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac)
  - [Get started with VS Code using C# and .NET Core on Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu)
  - [Working with C#](https://code.visualstudio.com/docs/languages/csharp)
- [如何為 .NET Core CLI 啟用 TAB 鍵自動完成](https://docs.microsoft.com/zh-tw/dotnet/core/tools/enable-tab-autocomplete) (PowerShell/Bash/Zsh)
