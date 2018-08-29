# comic-manager

<a href="https://komica2.net/51/src/1535498090201.png" target="_blank"><img src="https://komica2.net/51/src/1535498090201.png" style="width:50%" /></a>

島民版漫畫書庫管理程式

[Mega 下載點](https://mega.nz/#!0gZmyKoD!L2Liw0K0swzm6Te0zL2VvmxOVFH8-_nd8bn5uNdnhqw)

## 使用方式

<a href="http://komica2.net/51/src/1535527916425.png" target="_blank">基本使用方法圖解</a>

## 注意事項

1. 下載之後要先用文字處理器編輯 config.xml 這個檔案，填入
  - 外掛程式的路徑 (路徑不限中文)：
    - 支援免解壓的看圖程式 (例如 [CDisplayEx](http://www.cdisplayex.com/)，[HoneyView](https://tw.bandisoft.com/honeyview/) 等)
    - 網頁瀏覽器 (如果想使用右鍵網路搜尋功能)
    - 媒體播放軟體 (如果想左鍵播放影片檔)
  - 漫畫壓縮檔所在的目錄 (注意目前不支援子目錄)

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

2. 程式可以解析的檔名格式是 `[作者名] 本子標題 (tag1)(tag2)...`，標籤用圓括號 `(tag)` 或方括號 `[tag]` 都可以（注意要用半形字），標籤裡面可以包含其他括號。以下是幾個符合規則的檔名範例：
  
    [御免なさい]悪魔なしっぽ！（コミック エグゼ 10）[中国翻訳][DL版].zip
    
    [じゃが山たらヲ] いじめてみたい (COMIC 高 2017年10月号).rar
    
    [毛玉牛乳 (玉之けだま)] えるどえっち (アズールレーン) (中国翻訳).7z
    
    (成年コミック) [雑誌] COMIC 失楽天 2018年6月号 [DL版].rar
    
因為個人對會場資訊沒興趣，所以我自己的本子都會移掉這個標籤，程式也不會處理這塊，造成不便請見諒 (´・ω・`)

3. 程式內建數種排版方式 (renderer)，除了預設模式之外其他的都還在測試中

暫時先這樣，如果有其他問題或 bug 請在上面發 issue 回報，謝謝大家 ≡(　ε:)
