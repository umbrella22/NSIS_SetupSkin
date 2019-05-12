# NSIS_SetupSkin
NSIS打包工具，基于XML可自定义UI，基于[NSIS-UI](https://github.com/hilanmiao/NSIS-UI)修改而来

## 修改如下：
- 1、修改目录结构，使项目更加规范：
> 对图片文件统一归纳
> 对编译bat文件针对每个程序目录放在该目录下

- 2、修改函数调用，使项目更加规范，例如：
ui.nsh 73-76行

- 3、修改函数中代码块语句错误的bug：
ui.nsh 第70行

- 4、UI中白色背景时白色按钮不显示修改为黑色按钮可显示：
install.xml 24-32行

- 5、bat中删除文件时先判断是否存在

- 6、bat中遍历源程序文件夹时先判断是否为空：
makensiscode.bat 第45行

- 7、产品信息使用变量，避免输入多次可能输错：
songliwu.nsi 6-10行



## 目录结构
```
.
│  7z.dll                                   7z压缩dll
│  7z.exe                                   7z压缩主程序
│  makeapp.bat                              压缩FilesToInstall文件夹脚本
│  makensiscode.bat                         不压缩时遍历FilesToInstall文件夹生成编译需要的app.nsh文件
│  makeskinzip.bat                          压缩SetupScripts/*/skin文件夹
│  
├─FilesToInstall                            源程序文件夹
├─NSIS                                      NSIS主程序文件夹
├─OriginPlugin                              插件
└─SetupScripts                               项目UI配置目录
    │  commonfunc.nsh                        公共函数
    ├─nim                                    无复选框UI示例
    │  │  build-nim-nozip.bat                 不带压缩构建脚本
    │  │  build-nim.bat                       带压缩构建脚本
    │  │  licence.rtf                         产品许可文件
    │  │  license.txt
    │  │  logo.ico                            产品logo图标
    │  │  nim.nsi                             安装包产品信息定义,引用了ui.nsh
    │  │  ui.nsh                              UI函数
    │  │  uninst.ico                          卸载图标
    │  │  
    │  └─skin                                 UI配置
    │      │  configpage.xml                    配置页XML
    │      │  default.xml                       全局XML
    │      │  finishpage.xml                    安装完成页XML
    │      │  install.xml                       安装首页XML
    │      │  installingpage.xml                安装进行页XML
    │      │  licensepage.xml                   产品许可页XML
    │      │  msgBox.xml                        提示消息页XML
    │      │  uninstallfinishpage.xml           卸载完成页XML
    │      │  uninstallingpage.xml              卸载进行页XML
    │      │  uninstallpage.xml                 卸载首页XML
    │      │  
    │      ├─form                             公共文件，比如公用图片
    │      └─public                           独立部件文件
    │          ├─bk
    │          ├─button
    │          ├─caption
    │          ├─checkbox
    │          ├─edit
    │          └─vsrcollbar
    │                  
    └─songliwu                                   有复选框UI示例
        │  build-songliwu-nozip.bat              不带压缩构建脚本
        │  build-songliwu.bat                    带压缩构建脚本
        │  license.txt                           产品许可文件
        │  logo.ico                              产品logo图标
        │  songliwu.nsi                          安装包产品信息定义,引用了ui.nsh
        │  ui.nsh                                UI函数
        │  uninst.ico                            卸载图标
        │  
        └─skin                                 UI配置
            │  configpage.xml                    配置页XML
            │  default.xml                       全局XML
            │  finishpage.xml                    安装完成页XML
            │  install.xml                       安装首页XML
            │  installingpage.xml                安装进行页XML
            │  licensepage.xml                   产品许可页XML
            │  msgBox.xml                        提示消息页XML
            │  msgBox2.xml
            │  uninstallfinishpage.xml           卸载完成页XML
            │  uninstallingpage.xml              卸载进行页XML
            │  uninstallpage.xml                 卸载首页XML
            │  
            └─form                             公共文件，比如公用图片
```