[中文](README.md) | [Live demo!](https://sls-website-ap-beijing-imubol-1302315972.cos-website.ap-beijing.myqcloud.com/)

# Quick start

Make sure that you have the [Serverless Framework](https://www.serverless.com/framework/docs/providers/tencent/guide/installation/) installed. Clone this repo, and run the following command to build and deploy the entire application.

```
$ sls deploy
... ...
  website:       https://sls-website-ap-hongkong-kfdilz-1302315972.cos-website.ap-hongkong.myqcloud.com
  vendorMessage: null

63s › tencent-ocr-scf › "deploy" ran for 3 apps successfully.
```

Load the website URL in any web browser and start to use this function to identify objects in photos.


# Build your own OCR cloud function

Fork this repo and use the `Code | Open with Codespaces` button to launch Github Codespaces IDE in your browser. It may take a few minutes to start the first time. 

## Low code development

Once the Codespaaces IDE starts, you can make simple changes to the source code to customize it for your own applications.

* To change to a different language, add the new language's [traineddata file](https://github.com/tesseract-ocr/tessdata) to the `scf/` folder.
* Make changes to the language setting and data pre-processing and post-processing logic in `src/main.rs` file. 
* Make changes to the front end UI in the `website/content/index.html` file.

## Build

Open a `Terminal` window in the Codespaces IDE, and run the following command to build your cloud function.

```
$ ssvmup build --enable-aot
```

## Deploy

In the `Terminal` window, run the following commands to deploy the Tesseract OCR cloud function to the Tencent Cloud.

```
$ cp pkg/scf.so scf/

$ sls deploy
... ...
  website:       https://sls-website-ap-hongkong-kfdilz-1302315972.cos-website.ap-hongkong.myqcloud.com
```

Load the deployed URL in any web browser and have fun!

# Develop on your own computer

If you cannot or do not wish to use Github Codespaces, you can install the ssvmup and serverless framework toolchains on your own computer (or Docker image) to build and deploy the Tesseract OCR serverless functions.

[Install the ssvmup tool](https://www.secondstate.io/articles/ssvmup/)

Install the Serverless Framework via the NPM.

```
$ npm install -g serverless
```

That's it. You can now follow the Codespaces' build and deploy instructions above.

