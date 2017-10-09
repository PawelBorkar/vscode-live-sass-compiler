
# Live Sass Compiler

**_[If you like the extension, [please leave a review](https://marketplace.visualstudio.com/items?itemName=ritwickdey.live-sass#review-details), it puts a smile on my face.]_**

<!-- **_[If you found any bug or if you have any suggestion, feel free to report or suggest me.]_** -->

***[NOTE : From v1.0.0, the `liveSassCompile.settings.format`, `.savePath`, `.extensionName` settings are dropped. (See settings section for the new setting.)]***


[![VSCode Marketplace Badge](https://img.shields.io/vscode-marketplace/v/ritwickdey.live-sass.svg?label=VSCode%20Marketplace&style=flat-square)](https://marketplace.visualstudio.com/items?itemName=ritwickdey.live-sass) [![Total Install](https://vsmarketplacebadge.apphb.com/installs-short/ritwickdey.live-sass.svg?style=flat-square)](https://marketplace.visualstudio.com/items?itemName=ritwickdey.live-sass) [![Avarage Rating Badge](https://img.shields.io/vscode-marketplace/r/ritwickdey.live-sass.svg?style=flat-square)](https://marketplace.visualstudio.com/items?itemName=ritwickdey.live-sass) [![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](https://github.com/ritwickdey/vscode-live-sass-compiler/)

A VSCode Extension that help you to compile/transpile your SASS/SCSS files to CSS files at realtime with live browser reload.

![App Preview](./images/Screenshot/AnimatedPreview.gif)

## Usage/Shortcuts
1. Click to `Watch Sass` from Statusbar to turn on the live compilation and then click to `Stop Watching Sass` from Statusbar to turn on live compilation . 
![Statusbar control](./images/Screenshot/statusbar.jpg)

2. Press `F1` or `ctrl+shift+P` and type `Live Sass: Watch Sass` to start live compilation or, type `Live Sass: Stop Watching Sass` to stop a live compilation.
3. Press `F1` or `ctrl+shift+P` and type `Live Sass: Compile Sass - Without Watch Mode ` to compile Sass or Scss for one time.

## Features
* Live SASS & SCSS Compile.
* Customizable file location of exported CSS.
* Customizable exported CSS Style (`expanded`, `compact`, `compressed`, `nested`).
* Customizable extension name (`.css` or `.min.css`).
* Quick Status bar control.
* Exclude Specific Folders by settings. 
* Live Reload to browser (Dependency on `Live Server` extension).

## Installation
Open VSCode Editor and Press `ctrl+P`, type `ext install live-sass`.

## Settings
* ~~**`liveSassCompile.settings.format`:** To customize exported CSS style - _`expanded`_, _`compact`_, _`compressed`_ or _`nested`_.~~
    * ~~_Default is  `expanded`._~~

* ~~**`liveSassCompile.settings.savePath`:** To customizable file location of exported CSS. Set absulate path from workspace Root.`'/'` stands for your workspace root.~~
    * ~~_Example: `/subfolder1/subfolder2`. All generated CSS file will be saved at `subfolder2`._~~
    * ~~_NOTE: If destination folder does not exist, folder will be created as well._~~
    * ~~_Default value is `null`, CSS will be generated at same directory of every SASS/SCSS files._~~
* ~~**`liveSassCompile.settings.extensionName`:** To customize extension name (`.css` or `.min.css`) of generated CSS.~~ 
    * ~~_Default is `.css`._~~

* ***[NEW]***   **`liveSassCompile.settings.formats`** :  To setup Format (style), Extension Name & Save location for exported css [Multiple Format Supported].

    * *Format can be _`expanded`_, _`compact`_, _`compressed`_ or _`nested`_. _Default is  `expanded`._*

    * *Extension Name can be `.css` or `.min.css`. Default is `.css`.*
     
    * *Save location is relative from workspace root. Default value is `/` (workspace root).*
        
    * *Example :*
        
        ```json
            "liveSassCompile.settings.formats":[
                {
                    "format": "expanded",
                    "extensionName": ".css",
                    "savePath": "/css"
                },
                {
                    "format": "compressed",
                    "extensionName": ".min.css",
                    "savePath": "/dist/css"
                }
            ]
        ```

* **`liveSassCompile.settings.excludeList`:** To Exclude specific folders. All Sass/Scss files inside the folders will be ignored.
    * _default value :_
        ```json
            [ 
                "**/node_modules/**",
                ".vscode/**" 
            ]
        ```
    * You can use negative glob pattern.
        
        * _Example : if you want exclude all file except `file1.scss` & `file2.scss` from `path/subpath` directory, you can use the expression -_  
        
        ```json
        [
            "path/subpath/*[!(file1|file2)].scss"
        ]
        ```
* **`liveSassCompile.settings.includeItems`:** This setting is useful when you deals with only few of sass files. Only mentioned Sass files will be included. 

    * *NOTE: No need to include partial sass files.*
    * *Default value is `null`*
    * Example :
    ```json
        [
            "path/subpath/a.scss",
            "path/subpath/b.scss",
        ]
    ``` 
* **`liveSassCompile.settings.generateMap`:** Set it as `false` if you don't want `.map` file for compiled CSS. 
    * _Default is `true`._

## Extension Dependency 
This extension has dependency on _[Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)_ extension for live browser reload.

## What's new ?

* #### Version 1.0.0 (10.10.2017)
    * ***[New Features/settings [#10](https://github.com/ritwickdey/vscode-live-sass-compiler/issues/10)]*** Support for multiple extensionName, formats & save locations . *[Thanks to [Trinh Xuan Manh](https://github.com/ShadowFoOrm) for the suggestion and a Special Thanks to [Ibsenleo](https://github.com/ibsenleo) for  the PR [#16](https://github.com/ritwickdey/vscode-live-sass-compiler/pull/16).]*

    ***NOTE : Due to enable this feature, the `liveSassCompile.settings.format`, `.savePath`, `.extensionName` settings are dropped. [See settings section for the new setting.]***

* #### Version 0.5.1 (23.09.2017)
    * ***[Bug Fixed [#12](https://github.com/ritwickdey/vscode-live-sass-compiler/issues/12)]*** Sass files from excluded list was compiled on individual savings. _[Thanks [Braedin Jared](https://github.com/ImBaedin)]_

* #### Version 0.5.0 (25.08.2017)
    * ***[New Settings]*** `liveSassCompile.settings.generateMap` : Set it as `false` if you don't want `.map` file for compiled CSS. Default is `true`. *[[#9](https://github.com/ritwickdey/vscode-live-sass-compiler/pull/9) Thanks [Mark Hewitt](https://github.com/mhco) for the PR].*
    

## Changelog
To check full changelog click here [changelog](CHANGELOG.md).

## LICENSE
This extension is licensed under the [MIT License](LICENSE)

## FAQ (For Beginners)

### How to config the settings in my project?

Create a `.vscode` folder in the root of project. Inside of `.vscode` folder create a json file named `settings.json`.
Inside of the `settings.json`, type following key-value pairs. By the way you'll get intelli-sense.

```json
{
     "liveSassCompile.settings.formats":[
        {
            "format": "expanded",
            "extensionName": ".css",
            "savePath": "/css"
        },
        {
            "extensionName": ".min.css",
            "format": "compressed",
            "savePath": "/dist/css"
        }
    ],
    "liveSassCompile.settings.excludeList": [
       "**/node_modules/**",
       ".vscode/**"
    ],
    "liveSassCompile.settings.generateMap" : true
}
```