# comic-manager

<a href="https://komica2.net/51/src/1535498090201.png" target="_blank"><img src="https://komica2.net/51/src/1535498090201.png" style="width:50%" /></a>

島民版漫畫書庫管理程式

## 程式下載

(Windows 64bit portable)

<a href="https://kokorolove.github.io/comic-manager/comic-manager 2018-08-29 (no video support).rar" target="_blank">精簡版 (不支援影片檔案縮圖)</a>，檔案大小 416KB

<a href="https://kokorolove.github.io/comic-manager/comic-manager 2018-08-29 (with video support).rar" target="_blank">完整版 (支援影片檔案縮圖)</a>，檔案大小 30MB

完整版比精簡版多了兩個(很大的)視訊解碼用 DLL 檔，可以讓程式生成和編輯視訊檔案的預覽圖。把這兩個 DLL 拿掉就成了精簡版。

## 系統需求

- Windows 7/8/10
- .NET framework ver 4.6.1 or later (<a href="https://www.microsoft.com/net/download/dotnet-framework-runtime" target="_blank">下載最新版本</a>)

## 使用方式
 
- <a href="https://kokorolove.github.io/comic-manager/manual/images/manual.png" target="_blank">基本使用方法圖解</a>，等有空時再寫詳細一點 (´・ω・`) 
- 常用快速鍵：
    Esc (清除過濾，顯示所有檔案)， F5 (重新整理，可載入磁碟上新增加的檔案)， F2 (修改檔名或檔案標籤) 

## 更新歷程

2018-08-30
  - 支援子目錄 (可在視窗左上角檢視目錄樹狀圖)
  - 將程式分成支援和不支援影像縮圖兩個版本，降低檔案大小

## 注意事項

1. 下載之後要先用文字處理器編輯 config.xml 這個檔案，填入
  - 外掛程式的路徑 (路徑可支援中日文)：
    - 支援免解壓的看圖程式 (例如 [CDisplayEx](http://www.cdisplayex.com/)，[HoneyView](https://tw.bandisoft.com/honeyview/) 等)
    - 網頁瀏覽器 (如果想使用右鍵網路搜尋功能)
    - 媒體播放軟體 (如果想左鍵播放影片檔)
  - 漫畫壓縮檔所在的根目錄

  設定正確以後程式才能正常運作。以下是我在自己電腦上用的設定。

```XML
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <appSettings>
    <add key="RootDir" value="H:\COMIC;D:\DATA\COMIC;" />
    <add key="ComicViewer" value="C:\Program Files\CDisplayEx\CDisplayEx.exe" />
    <add key="WebBrowser" value="C:\Program Files (x86)\Google\Chrome\Application\chrome.exe" />
    <add key="MediaPlayer" value="C:\Program Files\DAUM\PotPlayer\PotPlayerMini64.exe" />
    <add key="StartupDir" value="H:\COMIC" />
  </appSettings>
</configuration>
```

2. 程式預設的檔名格式是 `[作者名] 本子標題 (tag1)(tag2)...`，標籤用圓括號 `(tag)` 或方括號 `[tag]` 都可以（注意括號要用半形字），標籤裡面可以包含其他括號，標籤之間也可以有空格。以下是幾個符合規則的檔名範例：
  
    [御免なさい]悪魔なしっぽ！(コミック エグゼ 10)[中国翻訳][DL版].zip
    
    [じゃが山たらヲ] いじめてみたい (COMIC 高 2017年10月号).rar
    
    [毛玉牛乳 (玉之けだま)] えるどえっち (アズールレーン) (中国翻訳).7z
    
    (成年コミック) [雑誌] COMIC 失楽天 2018年6月号 [DL版].rar
    
因為個人對會場資訊沒興趣，所以我自己的本子都會移掉這個標籤，等之後比較有空時再來處理這塊 (´・ω・`)

3. 程式內建數種排版方式 (renderer)，除了預設模式之外其他的都還在測試中

暫時先這樣，如果有其他問題或 bug 請在上面發 issue 回報，謝謝大家 ≡(　ε:)

## 已知問題
 
- 因為工具庫本身的限制，用 [Solid 模式](https://en.wikipedia.org/wiki/Solid_compression)壓縮的 RAR 或 7Z 檔案目前無法產生縮圖
- 縮圖的順序在某些操作步驟下會亂掉，問題修復前請先用<a href="https://kokorolove.github.io/comic-manager/manual/images/sort.png" target="_blank">這個方法</a>來重新排序

## 預定更新

- 修復縮圖排序的問題 (讓排序方式固定)
- 讓程式自動辨識檔名中的會場資訊，例如

    (C94) [NANIMOSHINAI (笹森トモエ)] TTH 19.5.zip

  當中的 "C94"，目前程式會把這個標籤當成作者。理想上程式要能自動判斷檔名裡的第一個標籤是會場還是作者。
