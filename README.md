# vue-practice
Vue前端框架學習紀錄，使用Vue2.0版本學習
# 環境搭建
安裝Visaul Studio Code 編輯器  
## 基本設定  
Code -> Preferences -> Settings -> 在USERSETTINGS複寫
```
{
    //縮排兩空白
    "editor.tabSize": 2,
    //主題亮色
    "workbench.colorTheme": "Visual Studio Light",
    //貼上自動排版
    "editor.formatOnPaste": true,
}
```
## 安裝插件
至Visaul Studio Code 的 EXTENSTIONS 安裝
#### Auto Close Tag
自動關閉HTML tag  
https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-close-tag   
#### Auto Rename Tag
自動重新命名對應的標籤  
https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag
#### Auto File Name
輸入檔案的時候，會提供路徑的提示  
https://marketplace.visualstudio.com/items?itemName=JerryHong.autofilename
#### vetur
開發vue必須的最主要工具  
https://marketplace.visualstudio.com/items?itemName=octref.vetur
#### ESLint
統一程式碼風格  
https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint
#### Image preview
自動在網址預覽圖片  
https://marketplace.visualstudio.com/items?itemName=kisstkondoros.vscode-gutter-preview

## 自動排版快捷鍵
```
On Windows Shift + Alt + F
On Mac Shift + Option + F
On Ubuntu Ctrl + Shift + I
```

## 利用官方 vue-cli 建立專案
1.npm install --global vue-cli  
2.vue init webpack my-project（接下來是專案的設定選項，默認即可。）  
3.cd project  
4.npm run dev  
5.至瀏覽器打開 http://localhost:8080/ 即可顯示畫面  

## Vue套件安裝
#### vue-resource
用於 http get / post / put / delete 使用
```  
npm install vue-resource --save
```

