# comic-manager

<a href="https://ericpony.github.io/comic-manager/manual/images/screenshot.png" target="_blank"><img src="https://ericpony.github.io/comic-manager/manual/images/screenshot.png"/></a>

島民版漫畫書庫管理程式

設計概念: 下載好的漫畫不必解壓縮，也不必手動建立資料夾分類。使用此漫畫管理程式，只需要把所有壓縮檔都放在同一個資料夾即可，程式會依照檔名內的標籤為漫畫分類。

本程式在第一次開啟時，會要求你設定一個支援免解壓的看圖工具 (例如 [CDisplayEx](http://www.cdisplayex.com/)，[HoneyView](https://tw.bandisoft.com/honeyview/) 等)。這個設定之後可以在設定檔 `config.xml` (位於程式所在目錄，程式啟動後會自動產生) 手動更改。

## 程式下載

- 最近更新：2022-07-09

    <a href="https://ericpony.github.io/comic-manager/comic-manager.rar" target="_blank">主程式 (免安裝)</a>，檔案大小 2MB

    <a href="https://ericpony.github.io/comic-manager/comic-manager - video thumb extension.rar" target="_blank?">視訊解碼外掛 (非必要)</a>，檔案大小 30MB
 
- 外掛是兩個視訊解碼用的 DLL 檔，把這兩個檔案和主程式放在一起，可以讓程式生成和編輯視訊檔案的預覽圖。

- 更新軟體版本時，只需重新下載主程式的執行檔就好。

## 更新紀錄

2022-07-09
  - 讓程式自動生成 `config.xml`，不再需要手動建立
  - 移除 Save 按鈕，往後自動儲存更動
  - 修正無法從右鍵選單改檔名的問題
  - 修正左下 Tag 列表的儲存問題

2018-11-07
  - 允許在搜尋欄位使用 AND 和 OR (見[使用說明](#使用說明))
  - 允許左上方的列表用右鍵新增/移除目錄 (會自動儲存)
  - 優化標籤編輯視窗

2018-11-05  
  - 支援批次新增/刪除/置換標籤
  - 支援安全刪檔 (搬移到資源回收桶)
  - 增加快速鍵 (見[使用說明](#使用說明))
  
2018-09-10
  - 允許用畫面下方的評分鈕為選取的檔案評分 (可一次選取多個檔案)
  - 修復左上搜尋框在打字時 focus 會跳掉的問題
  - 修復 [Issue #1](https://github.com/ericpony/comic-manager/issues/1#issuecomment-417949603) 提到的 config 錯誤  
  - 增加快速鍵 (見[使用說明](#使用說明))

2018-09-02
  - 修復排序有時候會跑掉的問題
  - 允許用右鍵選單來設定排序方式
  - 允許檔名中的第一個標籤代表年份 (例如 "C94")
 
2018-08-30
  - 支援子目錄 (可在視窗左上角檢視目錄樹狀圖)
  - 將程式分成支援和不支援影像縮圖兩個版本，降低檔案大小

## 系統需求

- Windows 7/8/10
- <a href="https://www.microsoft.com/net/download/dotnet-framework-runtime" target="_blank">.NET Framework Runtime ver 4.6.1 or later</a>

## 使用說明
 
- <a href="https://ericpony.github.io/comic-manager/manual/images/manual.png" target="_blank">基本使用方法圖解</a>，等有空時再寫詳細一點 (´・ω・`) 
- 常用快速鍵：  
    Esc：重設關鍵字，顯示所有檔案  
    F2： 修改檔名或檔案標籤  
    F3： 設定關鍵字，只顯示同作者的檔案  
    F4： 編輯預覽圖  
    F5： 重新整理 (可載入磁碟上新增加的檔案)<br />
    O： 使用系統預設的程式開啟檔案<br />
    E：  在檔案總管中檢視檔案<br />
    Delete： 將選取的檔案搬到資源回收桶<br />
    
- 關鍵字搜尋：
    - 搜尋不分大小寫
    - 目前支援 AND (&) 和 OR (|) 操作符，但兩者不能混用<br />
    例：`A & B` 可搜尋欄位內容同時包含 A 和 B 的檔案<br />
    例：`A | B | C` 可搜尋欄位內容包含 A 或 B 或 C 的檔案<br />
    - 當 Filter 選擇 Artist (搜尋作者)或 Title (搜尋標題)時，可使用引號 (") 搜尋完整字詞<br />
    例：使用 `"HELL"` 搜尋時 HELLO 會被過濾掉。
    
- 標籤編輯視窗

<a href="https://user-images.githubusercontent.com/42807610/47758647-d2d8be80-dca3-11e8-8588-dc48ae4f8718.png"><img src="https://user-images.githubusercontent.com/42807610/47758647-d2d8be80-dca3-11e8-8588-dc48ae4f8718.png"></a>

  - 程式會自動從漫畫壓縮檔的檔名中抽取標籤，選取檔案後按 F2 後會出現標籤編輯視窗，在視窗中可修改/增加/刪除檔案的標籤，清空文字欄位即可移除對應的標籤。

## 注意事項

1. 程式預設的檔名格式是 `[年份] [作者名] 本子標題 (tag1) (tag2)...`
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

2. 程式內建數種排版方式 (renderer)，除了預設模式之外其他的都還在測試中

  暫時先這樣，如果有任何操作問題/功能建議/錯誤回報，都歡迎在本專案[發 issue 討論](https://github.com/ericpony/comic-manager/issues/new) (需註冊 Github 帳號)，謝謝大家 ≡(　ε:)

## 已知問題
 
- 因為工具庫本身的限制，使用 [Solid 模式](https://en.wikipedia.org/wiki/Solid_compression)壓縮的檔案目前無法產生縮圖
- 雖然可以個別為每部漫畫評分，但是目前還無法依評分來排序檔案

## 預定更新

- 允許使用評分來排序檔案
