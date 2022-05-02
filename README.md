
[圖解-Redis：從應用到底層，一文幫你搞定](https://www.readfog.com/a/1635022294551203840)
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
> [Redis Geo 核心原理解析](https://mp.weixin.qq.com/s?__biz=MzI4NjI1OTI4Nw==&mid=2247485957&idx=2&sn=a5a75f2f9053cfd40df2d0d7a16389ef&scene=21#wechat_redirect)
> 
> bitmap  
>>          用戶簽到 -        key = 年份：用戶 id  offset = （今天是一年中的第幾天） % （今年的天數）
>>          統計活躍用戶  -   使用日期作爲 key，然後用戶 id 爲 offset 設置不同 offset 爲 0 1 即可。
>
> 發佈訂閱
> 
> 持久化
> >     RDB 持久化機制，是對 Redis 中的數據執行週期性的持久化。更適合做冷備
> >     AOF 機制對每條寫入命令作爲日誌，以 append-only 的模式寫入一個日誌文件中，因爲這個模式是只追加的方式，所以沒有任何磁盤尋址的開銷，所以很快，有點像 Mysql 中的 binlog。AOF 更適合做熱備。
>
> 恢復 -    啓動時會先檢查 AOF(數據更完整) 文件是否存在，如果不存在就嘗試加載 RDB。

#### 常見問題
> 緩存雪崩
> > 解決方案：
> > > 過期時間加上個隨機值，防止同一時間大量數據過期現象發生
> > > 熱點數據永遠不過期
> 緩存穿透
> > 解決方案：
> > > 單個 IP 每秒訪問次數超過閾值直接拉黑 IP
> 緩存擊穿
> > 解決方案：
> > > 設置熱點數據永遠不過期 加上互斥鎖也能搞定了
> 雙寫一致性
> 腦裂: 存在兩個不同的 master 節點就像一個大腦分裂成了兩個。其實在Hadoop 、Spark集羣中都會出現這樣的情況，只是解決方法不同而已 (用 ZK 配合強制殺死)。

#### Redis 集羣高可用
![image](https://user-images.githubusercontent.com/94338311/166179035-36b06ec3-0ed1-4097-b045-78779b523256.png)



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

