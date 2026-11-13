# 第五週 AI 使用紀錄

另存 AI_USAGE.md。每欄簡短填寫，不貼完整對話。使用真實服務、教師示範、模擬建議要據實標示。未使用 AI，第一欄寫「未使用」及原因，其餘可填不適用；本人課堂測試仍填 LAB_REPORT。不要上傳個資、密碼、憑證或未授權程式。

| 欄位 | 本人紀錄 |
|---|---|
| 使用工具／方式 | 待填：真實 AI 服務（Gemini）|
| 目的與提問摘要 | 待填：貼上第五週 MissionStep 與 MissionLog 骨架程式碼，請求協助完成 TODO 1 至 TODO 6（包含使用 this 儲存建構子參數、實作三個 getter、以內容比較判斷 isSuccessful()，以及在 MissionLog 中用單一 ArrayList<MissionStep> 記錄快照、回放與計算摘要）。|
| 建議與本人處理 | 待填：採納 AI 建議：在 MissionStep 建構子使用 this 區分欄位與參數，並使用 "OK".equals(this.result) 避免 NullPointerException；在 MissionLog 中每步 new MissionStep(...) 存入 history，並依講義要求調整 printReplay 的輸出格式使其與第四週一致。|
| 本人實際驗證 | 待填：編譯並執行預設腳本 {1, 1, 2}（初始能源 20、樣本 0），逐步回放與第四週完全一致，輸出 counts[0..3]=[0, 2, 1, 0]、steps=3, ok=3, rejected=0, ignored=0、lowest energy=6、最終 6/5/3 -> SUCCESS（battery=30.0）；另以 {3, 9, 0} 測試無效指令與返回，輸出 20/0/0 -> RETURNED，結果皆符合預期。 |

AI 的正確宣稱不能代替編譯執行。觀看教師展示只能記「教師示範觀察」；本人複驗才可記本人測試。

## 完整填寫範例（虛構／模擬）

以下為教師自編，假設一名學生做過這些操作，只示範填寫方式，不是你或作者的真實對話／實測證據。提交時刪除本範例，改填上表。

| 欄位 | 虛構填寫示範 |
|---|---|
| 使用工具／方式 | 教師模擬建議，未呼叫真實AI服務 |
| 目的與提問摘要 | 判讀「把電池本身存進歷史，之後再讀能源」是否保留當時狀態 |
| 建議與本人處理 | 我拒絕這項建議；兩個索引指向同一電池，不是兩個時間點的快照。在副本重現後，恢復每步建立StepCard並保存當時能源 |
| 本人實際驗證 | SnapshotDemo錯誤副本印出19/19及same object=true；恢復後兩筆command/energy為1/14、3/19，current=19、separate records=true。再跑{1,1,2}得6/5/3 SUCCESS、{3,9,0}得20/0/0 RETURNED，完整輸出放LAB_REPORT F3 |
