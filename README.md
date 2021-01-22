[English](README-en.md) | [Live demo!](https://sls-website-ap-beijing-imubol-1302315972.cos-website.ap-beijing.myqcloud.com/)

# 快速开始

首先请确认已经安装了 [Serverless Framework](https://www.serverless.com/framework/docs/providers/tencent/guide/installation/) . Clone 这个 repo，然后用下面的命令部署整个云原生应用！

```
$ sls deploy
... ...
  website:       https://sls-website-ap-hongkong-kfdilz-1302315972.cos-website.ap-hongkong.myqcloud.com
  vendorMessage: null

63s › tencent-ocr-scf › "deploy" ran for 3 apps successfully.
```

在浏览器中加载网站 URL，就开始使用函数来识别照片中的对象啦。

# 创建你自己的文本识别云函数

Fork 这个 repo，使用 `Code | Open with Codespaces` 按钮来在浏览器中打开 Github Codespaces IDE 。第一次启动时，需要花费几分钟。 

## 低代码开发

一旦 Codespaces IDE 启动了, 你就可以根据自己的应用程序需求来对源代码进行修改，自定义函数。

* 要识别另一种语言，把该语言的 [traineddata file](https://github.com/tesseract-ocr/tessdata) 加入到 `scf/` 目录下.
* 在 `src/main.rs` 文件中更改语言设置以及数据预处理和后处理逻辑。
* 在 `website/content/index.html` 文件中对前端UI进行更改。

## 创建

在 Codespaces 打开 `Terminal` 窗口, 然后运行下面的命令行来创建云函数。

```
$ ssvmup build --enable-aot
```

## 部署

在 `Terminal` 窗口，运行下面的命令行将 Tesseract OCR 云函数部署到腾讯云上。

```
$ cp pkg/scf.so scf/

$ sls deploy
... ...
  website:       https://sls-website-ap-hongkong-kfdilz-1302315972.cos-website.ap-hongkong.myqcloud.com
```

在浏览器内加载部署好的 URL。 Have fun!

# 在本地机器上部署

如果你不能或不想使用 Github Codespaces，那可以在自己的计算机（或Docker映像）上安装 ssvmup 和 serverless framework 工具链来构建和部署文本识别 serverless 函数。
[安装 ssvmup 工具](https://www.secondstate.io/articles/ssvmup/)

通过 NPM 安装 Serverless Framework。

```
$ npm install -g serverless
```

准备工作已经做完了，现在你可以参照上文提到的 Codespaces 的创建和部署教程来创建自己的云函数。

