# 概念

事件風暴是一種基於研討會的方法，用於快速找出軟體程序領域中發生的情況。與其他方法相比，它非常輕巧，並且不需要程式技術就可使用。結果在寬牆上以便利貼表示。業務流程作為一系列域事件被顯示出來，這些事件被表示為橙色便利貼。它是由Alberto Brandolini在領域驅動設計的背景下發明的。


# 階層

進行順序按照階層從 Big Picture 開始與領域專家討論核心的用戶行為，接著到 Process Modeling 補充更多的規則、行動，最後才是 Software Design

![image](uploads/09f733ce025962a8502f249294dd0812/image.png)

# 注意事項
在討論過程中，務必記得

1. 不要出現技術用語，例如資料庫怎麼儲存、實作要套什麼 Design Patten
1. 不要被 UI 綁架了!
1. 不要被 DB 綁架 - 任務驅動而非指令驅動

# 順序
- Big Picture - 加入 Role / Externel System
- Process Modeling - 加入 Command / Read Model
- Process Modeling - 加入Policy
- Software Design - 加入 Model


![d2YUQjhYXRxYj4-CI1goBxzmuimDiWJryv_oKbPe6gp0IltyyYk_-GfLA0cW25X4CkZQyxdYueDn_pSlGw6dfu1yafSpvnnqp9BOfBmcdseGb-tq82NCA-NV9wkCf1Hjkn7EHztirMM__1_](uploads/4ad521429a5dcc19d8ee740b9f38237e/d2YUQjhYXRxYj4-CI1goBxzmuimDiWJryv_oKbPe6gp0IltyyYk_-GfLA0cW25X4CkZQyxdYueDn_pSlGw6dfu1yafSpvnnqp9BOfBmcdseGb-tq82NCA-NV9wkCf1Hjkn7EHztirMM__1_.jpg)

| header | header | header |
| ------ | ------ | ------ |
| ![XroSL59oHrT_zQ1Vcv4zyW5gpQppQqoDzSmJVRUtmBpl6Lwfmy9mETb4agAXSs1--R8I03AhP-90P_9KBvRvMJ7lJWeZGpPaGOx0rD_AnGjJ6kTXKqiEX49iZG2zk7Ez0qrXpMiFRmk](uploads/7ed134efa3eb6568f55bdcd6c57c0498/XroSL59oHrT_zQ1Vcv4zyW5gpQppQqoDzSmJVRUtmBpl6Lwfmy9mETb4agAXSs1--R8I03AhP-90P_9KBvRvMJ7lJWeZGpPaGOx0rD_AnGjJ6kTXKqiEX49iZG2zk7Ez0qrXpMiFRmk.jpg) | ![TC9uK0ClN0fd04E-11pvIYMTmC3gS0CLTJ8p1M8_FPZjRpFQQ16DE5Xwf0zvEAR2bwIteme460pr9w4QO4S8ZB089I8Ha2kUllGGMKUbYyCyMcpkL6R708cjMJeKTZuI5ug0yhCkgyA](uploads/3f5cbab05d315ab9d2d438fef2157321/TC9uK0ClN0fd04E-11pvIYMTmC3gS0CLTJ8p1M8_FPZjRpFQQ16DE5Xwf0zvEAR2bwIteme460pr9w4QO4S8ZB089I8Ha2kUllGGMKUbYyCyMcpkL6R708cjMJeKTZuI5ug0yhCkgyA.jpg) |![h0q1onX1OPGuqKndxnC2sqMcCiucfWfM0l3mYyoJvLxpkG4nnWwxWyPHxKIy78WS0Y-liZeUDN0az8gr7nhz-BDqMJdB39flGnUqsdTv8p13p--AWXANZ_fzHhEUcuutFl261N1xhxs](uploads/4d271308b59c13febdea3e3024acd4f3/h0q1onX1OPGuqKndxnC2sqMcCiucfWfM0l3mYyoJvLxpkG4nnWwxWyPHxKIy78WS0Y-liZeUDN0az8gr7nhz-BDqMJdB39flGnUqsdTv8p13p--AWXANZ_fzHhEUcuutFl261N1xhxs.jpg)|
| ![B9nnDnDCqOoQs081D-JnXpyb1SNjWuz5y_hyNuLPnK2dD7n22QKfSjnniQ9L7ZuEQKelsMcQBpTQC7NYscgA3rD-Z1XDtiXAcLK56hdrJ6vbB1AAZ4ryMhUa7THLPeqlV7UMrxACOGk](uploads/30c2f99aa717130ddd9572df98200d25/B9nnDnDCqOoQs081D-JnXpyb1SNjWuz5y_hyNuLPnK2dD7n22QKfSjnniQ9L7ZuEQKelsMcQBpTQC7NYscgA3rD-Z1XDtiXAcLK56hdrJ6vbB1AAZ4ryMhUa7THLPeqlV7UMrxACOGk.jpg) | ||

### picture that explains everything

![image](uploads/3ff380d59d23c512f70d14f34f5a1483/image.png)


## 參考資料

[領域驅動設計與簡潔架構入門實作班」上課筆記與心得：關於敏捷、 DDD、 Event Storming 與 Clean Architecture - 上](https://yuanchieh.page/posts/2022/2022-01-14-%E9%A0%98%E5%9F%9F%E9%A9%85%E5%8B%95%E8%A8%AD%E8%A8%88%E8%88%87%E7%B0%A1%E6%BD%94%E6%9E%B6%E6%A7%8B%E5%85%A5%E9%96%80%E5%AF%A6%E4%BD%9C%E7%8F%AD%E4%B8%8A%E8%AA%B2%E7%AD%86%E8%A8%98%E8%88%87%E5%BF%83%E5%BE%97%E9%97%9C%E6%96%BC%E6%95%8F%E6%8D%B7-ddd-%E8%88%87-event-storming-%E4%B8%8A/)


