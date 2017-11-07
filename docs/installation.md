# 如何使用: 本地编译

本页面介绍如何在本地使用模板。

* [环境配置](#环境配置)
   * [Linux 系统](#linux-系统)
      * [LaTeX 环境](#latex-环境)
      * [字体问题](#字体问题)
   * [Windows 系统](#windows-系统)
      * [LaTeX 环境](#latex-环境-1)
      * [字体问题](#字体问题-1)
   * [MacOS 系统](#macos-系统)
      * [LaTeX 环境](#latex-环境-2)
      * [字体问题](#字体问题-2)
* [模板获取](#模板获取)
   * [终端中克隆最新版](#终端中克隆最新版)
   * [压缩包下载](#压缩包下载)
* [编译模板](#编译模板)

## 环境配置

### Linux 系统

#### LaTeX 环境

SJTUThesis 使用 XeLaTeX 进行编译，因此需要 LaTeX 的运行环境。[TeX Live](https://www.tug.org/texlive/) 是 TeX 及其相关程序在 GNU/Linux 及其他类 Unix 系统、Mac OS X 和 Windows 系统下的⼀套发⾏版，因此可以访问其主页进行安装，安装过程可参考 [TeX Live - Quick install](https://www.tug.org/texlive/quickinstall.html)。

详细可查看 [TeX Live 安装指南](https://github.com/weijianwen/SJTUThesis/wiki/texlive-%E5%AE%89%E8%A3%85%E6%8C%87%E5%8D%97)

#### 字体问题

SJTUThesis 使用 [CTeX](https://www.ctan.org/pkg/ctex?lang=en) 提供中文支持，共需要五种字体，分别是一套英文字体，和宋体、仿宋、黑体、楷体四种中文字体。

因为大部分 Linux 发行版对中文支持的方案都不同，因此推荐 Linux 用户在使用模板之前安装 [Fandol](https://www.ctan.org/pkg/fandol) 的四种中文字体（宋体、仿宋、黑体、楷体的正常体）和 [Tex Gyre Termes](http://www.ctan.org/tex-archive/fonts/tex-gyre/fonts/opentype/public/tex-gyre) 英文字体（斜体、粗体、正常体、粗斜体均需要下载安装）。

Tex Gyre Termes 字体是遵循 [GUST Font Source License](http://www.ctan.org/license/gfsl) 的，而 Fandol 字体是开源在 [GNU Gen­eral Public Li­cense](https://www.gnu.org/licenses/licenses.html) 下的。可以避免由字体带来的版权问题。

除此之外，还有其他的字体选择，包括 Adobe 的中文字体 AdobeSongStd, AdobeKaitiStd, AdobeHeitiStd, AdobeFangsongStd 等。因为涉及版权，如果要使用请自行下载。

### Windows 系统

#### LaTeX 环境

SJTUThesis 使用 XeLaTeX 进行编译，因此需要 LaTeX 的运行环境，Windows 用户可以安装 [CTeX 套装（包含完整版 MiKTeX）](http://www.ctex.org/CTeXDownload)。此外，推荐使用 [Babun](http://babun.github.io/) 作为命令行终端。Babun 已默认安装有这些工具：git(用于版本控制)、GNUmake(用于编译控制)、perl(用于字数统计)。

详细可查看 [TeX Live 安装指南](https://github.com/weijianwen/SJTUThesis/wiki/texlive-%E5%AE%89%E8%A3%85%E6%8C%87%E5%8D%97)

#### 字体问题

SJTUThesis 使用 [CTeX](https://www.ctan.org/pkg/ctex?lang=en) 提供中文支持，共需要五种字体，分别是一套英文字体，和宋体、仿宋、黑体、楷体四种中文字体。

Windows 系统有内置中文字体，可以直接使用。但需要安装 [Tex Gyre Termes](http://www.ctan.org/tex-archive/fonts/tex-gyre/fonts/opentype/public/tex-gyre) 英文字体（斜体、粗体、正常体、粗斜体均需要下载安装）。

除此之外，还有其他的字体选择，包括 [Fandol](https://www.ctan.org/pkg/fandol) 和 Adobe 的中文字体等，如有需要请自行下载安装。

### MacOS 系统

#### LaTeX 环境

SJTUThesis 使用 XeLaTeX 进行编译，因此需要 LaTeX 的运行环境，MacOS 用户可以安装 [MacTeX](https://www.tug.org/mactex/)。

详细可查看 [TeX Live 安装指南](https://github.com/weijianwen/SJTUThesis/wiki/texlive-%E5%AE%89%E8%A3%85%E6%8C%87%E5%8D%97)

#### 字体问题

MacOS 系统有内置中文字体，可以直接使用。但需要安装 [Tex Gyre Termes](http://www.ctan.org/tex-archive/fonts/tex-gyre/fonts/opentype/public/tex-gyre) 英文字体（斜体、粗体、正常体、粗斜体均需要下载安装）。

除此之外，还有其他的字体选择，包括 [Fandol](https://www.ctan.org/pkg/fandol) 和 Adobe 的中文字体等，如有需要请自行下载安装。

## 模板获取

根据「系统需求」中情形选择适合你系统情况的分支，然后根据情况选择 git 克隆最新版代码或者下载稳定版压缩包。

### 终端中克隆最新版

```bash
git clone https://github.com/dyweb/SJTUThesis.git
```

如果之前有克隆过此模板但是想与 GitHub 上的最新版本同步，以`master`分支为例，执行以下命令更新到最新版。

```bash
git pull origin master
```

若是自己 fork 后克隆下来的，则执行以下命令。

```bash
git pull upstream master
```

## 编译模板

针对不同的系统和需求，需要修改 thesis.tex 文件：

```tex
% \documentclass[
%   bachelor|master|doctor,           % 必选项
%   fontset = {none|adobe|fandol|
%   founder|mac|ubuntu|windows|
%   windowsnew|windowsold|...},       % 字体选择，需要先安装对应字体
%   oneside|twoside,                  % 单面打印，双面打印(奇偶页交换页边距，默认)
%   openany|openright,                % 可以在奇数或者偶数页开新章|只在奇数页开新章(默认)
%   zihao=-4|5,                       % 正文字号：小四、五号(默认)
%   review,                           % 盲审论文，隐去作者姓名、学号、导师姓名、致谢、发表论文和参与的项目
%   submit                            % 定稿提交的论文，插入签名扫描版的原创性声明、授权声明
% ]
```

其中字体的选择要视系统字体的安装情况而定。其中 fandol 选项是使用 fandol 字体，founder 选项是使用方正字体，mac 选项是使用 macOS 系统自带字体，ubuntu 选项是使用 ubuntu 自带字体（有 bug，不推荐），windows 选项是使用 Windows 系统自带字体。

随后编译模板，生成学位论文PDF文件。GNUMake将调用`latexmk`程序，自动完成模板的多轮编译。

```bash
make pvc
```

定稿后可使用以下命令生成最终版本。

```bash
make clean thesis.pdf
```

若需要生成用于提交盲审的论文(隐去作者、导师等信息)，可在`thesis.tex`中为`sjtuthesis`文档类添加`review`选项。 若需要生成包含“原创性声明扫描件”和“授权书”签名扫描件的学位论文，请将扫描件分别保存为`pdf/origignal.pdf`和`pdf/authorization.pdf`，然后添加`submit`选项重新编译模板。

Windows 用户双击`compile.bat`即可完成编译过程，生成`thesis.pdf`，不依赖于 GNUMake，但推荐使用 GNUMake 的方式进行编译。

## 字数统计

运行如下命令:

```bash
make wordcount
```