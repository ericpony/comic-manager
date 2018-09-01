# comic-manager

<a href="https://komica2.net/51/src/1535498090201.png" target="_blank"><img src="https://komica2.net/51/src/1535498090201.png" style="width:50%" /></a>

島民版漫畫書庫管理程式

## 程式下載

(Windows 64bit portable)

<a href="https://kokorolove.github.io/comic-manager/comic-manager.rar?ver=2018-08-31" target="_blank">主程式</a>，檔案大小 416KB

<a href="https://kokorolove.github.io/comic-manager/comic-manager - video thumb extension.rar" target="_blank?">視訊解碼外掛</a>，檔案大小 30MB
 
- 外掛是兩個視訊解碼用的 DLL 檔，把這兩個 DLL 檔案和主程式放在一起，可以讓程式生成和編輯視訊檔案的預覽圖。
- 更新軟體版本時只需要重新下載主程式就好。
 
## 系統需求

- Windows 7/8/10
- <a href="https://www.microsoft.com/net/download/dotnet-framework-runtime" target="_blank">.NET Framework Runtime ver 4.6.1 or later</a>

## 使用方式
 
- <a href="https://kokorolove.github.io/comic-manager/manual/images/manual.png" target="_blank">基本使用方法圖解</a>，等有空時再寫詳細一點 (´・ω・`) 
- 常用快速鍵：
    Esc (清除過濾，顯示所有檔案)， F5 (重新整理，可載入磁碟上新增加的檔案)， F2 (修改檔名或檔案標籤) 

## 更新紀錄
 
2018-08-31
  - 允許檔名中的第一個標籤代表年份 (例如 "C94")
 
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

2. 程式預設的檔名格式是 `[年份] [作者名] 本子標題 (tag1) (tag2)...`
  - 第一個標籤可以是年份 (例如"C92") 或作者。如果第一個標籤不是作者，則預設把第二個標籤視為作者。
  - 標籤用圓括號 `(tag)` 或方括號 `[tag]` 都可以（注意括號要用半形字）
  - 標籤裡面可以包含其他括號，標籤之間可以任意空格。
  
  以下是幾個符合規則的檔名範例：

    (C94) [NANIMOSHINAI (笹森トモエ)] TTH 19.5.zip
  
    (例大祭15) [りとる☆はむれっと(きぃら～☆)] 古明地さとりのイケナイあそび (東方Project).rar
  
    [御免なさい]悪魔なしっぽ！(コミック エグゼ 10)[中国翻訳][DL版].zip
    
    [じゃが山たらヲ] いじめてみたい (COMIC 高 2017年10月号).rar
    
    [毛玉牛乳 (玉之けだま)] えるどえっち (アズールレーン) (中国翻訳).7z
    
    (成年コミック) [雑誌] COMIC 失楽天 2018年6月号 [DL版].rar
    
  注意：程式雖然可以辨認年份標籤，但是年份不會顯示在檔案資訊和標籤欄位裡。

3. 程式內建數種排版方式 (renderer)，除了預設模式之外其他的都還在測試中

  暫時先這樣，如果有其他問題或 bug 請在上面發 issue 回報，謝謝大家 ≡(　ε:)

## 已知問題
 
- 因為工具庫本身的限制，使用 [Solid 模式](https://en.wikipedia.org/wiki/Solid_compression)壓縮的檔案目前無法產生縮圖
- 縮圖的順序在某些操作步驟下會亂掉，問題修復前請先用<a href="https://kokorolove.github.io/comic-manager/manual/images/sort.png" target="_blank">這個方法</a>來重新排序

## 預定更新

- 修復縮圖排序的問題 (讓排序方式固定)
