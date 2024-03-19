ClickOnce does not have prerequisite for asp.net runtime 8.03.

https://stackoverflow.com/questions/74142462/clickonce-prerequisite-for-asp-net-core-runtime-6-0-10-x64


Add the prerequisite for VS:

- create a directory structure
  - Asp.Net_runtime_8.0.3_x64\product.xml
  - Asp.Net_runtime_8.0.3_x64\NetCoreCheck.exe
    - find it at at (VS install directory)\MSBuild\Microsoft\VisualStudio\BootstrapperPackages\net7coreruntime_x64
      - "c:\Program Files\Microsoft Visual Studio\2022\Community\MSBuild\Microsoft\VisualStudio\BootstrapperPackages\net8desktopruntime_x86\.." 
    - Asp.Net_runtime_8.0.2_x64\en\package.xml
- copy the files into c:\Program Files (x86)\Microsoft SDKs\ClickOnce Bootstrapper\Packages
    - you need admin rights
- now the new dependency should appear in VS
    - you do not have to restart VS, just press in "project / publish" and the "more actions / edit"
- if there is a new version then you should create a new directory structure with modified xml files
    - update HomeSite in product.xml
      - New link for HomeSite: "https://dotnet.microsoft.com/en-us/download" / "All .Net 8.0 versions" / "ASP.NET Core Runtime 8.0.3, Windows x64" / "Direct link, Copy"
