# 软件安装和包管理器

## 普通用户安装软件

作为电脑的普通用户，典型的安装软件方式是：

* Windows
  * 下载安装包exe文件，双击，根据提示，一步步去安装
  * 下载了免安装的，解压后直接使用，无需安装。
* Linux
  * 方式1：下载`源码`自己`编译`和`安装`
  * 方式2：用各种`包管理器`去`install`安装

不同系统，有各自常用的包管理器，去用于安装软件：

## 包管理器

### 不同系统的常见包管理器

* 系统
  * `Mac`
    * `Homebrew`
      * `brew install xxx`
    * `MacPorts`
      * `port install xxx`
  * `Linux`
    * `Debian`/`Ubuntu`/`Termux`
      * `apt`
        * `apt-get install xxx`
    * `Red Hat`/`CentOS`
      * `yum`
        * `yum install xxx`
    * `FreeBSD`/`Termux`
        * `pkg install xxx`

其中Linux由于有很多发行版，比较特殊，所以专门再详细解释：

#### Linux系统中的包管理器

Linux有很多不同发行版，每个发行版基本都有自己的用于安装软件的`包管理器`=`包管理系统`=`package management tool`。常见的一些有：

* `Debian`/`Ubuntu`：
  * 软件包格式：`deb`
  * 包管理工具：`dpkg`
  * 前端工具：`apt`
* `Fedora`/`Red Hat Enterprise Linux`/`CentOS`/`openSUSE`/`Mandriva Linux`/`Mageia`
  * 软件包格式：`rpm`
  * 前端工具
    * `Fedora`：`dnf`
    * `Red Hat Enterprise Linux`/`CentOS`：`yum`
    * `openSUSE`：`ZYpp`
    * `Mandriva Linux`/`Mageia`：`urpmi`

#### 举例

* `vlc`
  * `Debian`/`Ubuntu`/`Termux`
    * `apt-get install vlc`
  * `Red Hat`/`CentOS`
    * `yum install vlc`
  * `FreeBSD`/`Termux`
    * `pkg install vlc`
* `sshfs`
  * `CentOS`
    * `yum install sshfs`
  * `Fedora` 22+
    * `dnf install sshfs`
  * `Debian`/`Ubuntu`
    * `sudo apt-get install sshfs`

补充说明：

* 如果安装期间缺少权限，则往往要加上su或sudo以管理员身份才能安装
  * 举例
    ```bash
    sudo apt-get install vlc
    sudo yum install vlc
    ```

### 各种编程语言的常见包管理器

* 编程语言
  * `Python`
    * `pip`
      * 典型用法：
        * `pip install xxx`
      * 私有源
        * `pypiserver`
      * `pypi`
        * `pipenv`
          * `pipenv install xxx`
            * 配置文件：`Pipfile`
    * `Mac`的`iOS`: `Swift`/`Objective-C`
      * `Carthage`
        * `carthage update`
          * 配置文件：`Cartfile`
      * `Cocoapods`
        * `pod install`
          * 配置文件：`Podfile`
    * `Javascript`
      * `npm`
        * 用法：`npm install xxx`
        * 配置文件：`package.json`
      * `yarn`
        * `yarn add xxx`
      * `Bower`
        * `bower install xxx`
    * `PHP`
      * `composer`
        * `composer install`
          * 配置文件：`composer.json`
    * `Java`
      * `Maven`
        * 典型用法
          * 配置文件：`pom.xml`
          * 安装：
              * `mvn install`
        * 私有仓库=私服=公司内部的源
          * `Nexus`
      * `gradle`
        * 配置文件：`build.gradle`
        * 运行：`gradle xxx`
    * `Ruby`
      * `gem`
        * 配置文件：`Gemfile`
    * `.Net`
      * `NuGet`
        * 配置文件：`nupkg`

补充说明：

关于镜像和源：

* 综合=全能
  * `GitHub Package Registry`
    * 支持：
      * `JavaScript`：`npm`
      *  `Java`：`Maven`
      * `Ruby`：`RubyGems`
      * `.NET`：`NuGet`
      *  `Docker镜像`
      * 将要支持：
        * `Python`
        * `PHP`
