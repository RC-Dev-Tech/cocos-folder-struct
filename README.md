# ![](https://drive.google.com/uc?id=10INx5_pkhMcYRdx_OO4rXNXxcsvPtBYq) Cocos Creator 版本控制

---

<!--ts-->
## 目錄
* [簡介](#簡介)
* [assets](#assets-資源目錄)
* [build](#build-編譯目錄)
* [library](#library-資源庫)
* [local](#local-本地設置)
* [profiles](#profiles-編輯配置)
* [extensions](#extensions-擴充插件)
* [settings](#settings-專案設置)
* [temp](#temp-暫存資料夾)
* [config](#config-設定檔)
<!--te-->

---

## 簡介
這邊簡單介紹在 Cocos Creator 專案項目中的資料夾結構. <br>
以及在做版控的時候，哪些檔案是屬於自動產生，哪些檔案需要上傳.<br>

---

***資料夾結構如下:***
- assets：資源目錄
- build：編譯目錄
- library：導入資源目錄後所生成的目錄
- local：本地配置目录 
- profiles：编辑器資源配置
- temp：臨時目錄<br>
.gitignore：版控檔案<br>
package.json：套件配置檔案<br>
tsconfig.json：typescript配置檔案

---

## assets (資源目錄)
- 主要是用來放置所有的遊戲資源、腳本和第三方套件的地方.<br>
- 只有放在assets目錄下的資源，才會被顯示在編輯器的資源管理器中.<br>
- asset中的每一個檔案，包含資料夾，都會生成一個相同名字的.meta檔案，這個是用來儲存對應的資源配置跟訊息索引用. <br>
- 如果是第三方工具的設計編輯檔案，像是TexturePacker的.tps文件，或Photoshop的.psd文件，可以選擇放在assets外面管理.<br>

```diff
+ 版本控制: 整個資料夾含底下的資源跟.meta檔案都要上傳.
```

---

## build (編譯目錄)
- 在編輯器的選單中指定平台並執行發布後，會產生該資料夾，並存放所有建置後的相關檔案.<br>

```diff
- 版本控制: 由編輯器自動生成，所以不用上傳.
```

---

## library (資源庫)
- 該資料夾是編輯器在導入assets資料夾中的資源所產生的.<br>
- 其存放的資源格式會被轉換成最終遊戲被發布時所需要的格式.<br>

```diff
- 版本控制: 由編輯器自動生成，所以不用上傳.
```

---

## local (本地設置)
- 該資料夾主要存放本機上的配置內容，包括編輯器的面板佈局、窗口大小、位置等資訊.

```diff
- 版本控制: 個人編輯器使用，所以不用上傳.
```

---

## profiles (編輯配置)
- 該資料夾主要存放編輯器中的配置資訊，包括場景的配置資訊以及所要輸出的平台建構資訊等.

```diff
+ 版本控制: 整個資料夾含底下的資源都要上傳.
```

---

## extensions (擴充插件)
- 該資料夾主要用來放置自定義的擴充插件.<br>
- 該資料需手動創建. <br>
- 如要卸載擴充的插件，只要在資料夾中刪除對應的套件即可. <br>

```diff
+ 版本控制: 當多人開發並共用插件時，整個資料夾含底下的套件都要上傳.
```

---

## settings (專案設置)
- 該資料夾主要存放專案項目中的一些設定資訊.

```diff
+ 版本控制: 當多人開發需要同步項目設置時，其資料夾就要上傳.
```

---

## temp (暫存資料夾)
- 該資料夾為Cocos Creator在運行時，所產生的一個臨時資料夾，主要拿來存放一些緩衝檔案.
- 該資料夾在關閉Cocos Creator就可以刪除.

```diff
- 版本控制: 由編輯器自動生成暫存使用，所以不用上傳.
```

---

## config (設定檔）
- .gitignore：版控檔案
  - 主要用來設定哪些檔案不需要被提交到git檔案庫上.
- package.json：套件配置檔案
  - 該檔案是nodejs的套件配置檔案，但是放在cocos creator這邊會被拿來和assets資料夾一起作為驗證.
  - 一般使用的情況下，是不用理會到這個檔案，除非有使用到第三方的npm套件.
- tsconfig.json：typescript配置檔案
  - 該檔案是用來設置typescript的一些設定. 

```diff
+ 版本控制: 這三個檔案都需要上傳至版控系統.
```

---
<!--ts-->
#### [目錄 ↩](#目錄)
<!--te-->
