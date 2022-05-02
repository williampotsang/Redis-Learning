

> String  字符串     - 源碼中用SDS(simple dynamic string) 封裝 char[]，這是是 Redis 存儲的最小單元，一個 SDS 最大可以存儲 512M 信息。
> 
> List    列表    
> 
> Hash              - K 絕對是字符串對象，而 V 可以是 String、List、Hash、Set、ZSet 任意一種。 (hash 的底層主要是採用字典 dict 的結構)
> 
> Set     集合      - 可以認爲是沒有 Value 的 Dict
> 
> ZSet    有序集合  -  Zset 用的就是可以跟二叉樹媲美的跳躍表來實現有序
> 
[圖解-Redis：從應用到底層，一文幫你搞定](https://www.readfog.com/a/1635022294551203840)

---
#### Redis 是一個開源、BSD 許可的高級鍵值存儲。它通常被稱為數據結構服務器，因為鍵可以包含字符串、散列、列表、集合和排序集合。Redis 是用 C 語言編寫的。本教程提供了對 Redis 概念的良好理解，這是創建和部署高度可擴展且以性能為導向的系統所必需的
[Redis教學](https://www.1ju.org/redis/redis-quick-guide)

---
#### 應用:短網址系統ㄝ, 網站點擊統計系統, 高即時性排名系統
[技術共筆-資料庫的好夥伴：Redis](https://blog.techbridge.cc/2016/06/18/redis-introduction/)

---
#### Redis是C語音編寫的基於記憶體的數據結構存儲系統。它可以當作資料庫、快取和消息中間件。 它支援多種類型的數據結構，如 字元串（strings），列表（lists）， 字典（dictht），集合（sets）， 有序集合（sorted sets）。通常我們在項目中可以用它來做快取、記錄簽到數據、分散式鎖等等。
[小白也能看懂的Redis教學基礎篇——redis基礎數據結構](https://codingnote.cc/zh-tw/p/215877/)

---
[Redis基礎知識](https://www.twblogs.net/a/5d14997abd9eee1ede050778)

