# 環境安裝與 AMQP 基礎

## 學習目標
- 理解 AMQP 基本概念與名詞
- 啟動 RabbitMQ（含管理介面）並建立 vhost、user、permission
- 以 UI 觀測 queue 與訊息計數

## 背景知識
- AMQP 基本模型：Producer、Exchange、Queue、Consumer
- Virtual host 隔離與權限模型
- 管理介面導覽與健康檢查

## 架構描述（文字）
- 元件：Producer、Exchange、Queue、Consumer
- 關係：Producer 將訊息送入 Exchange，依綁定規則路由到 Queue，再由 Consumer 取用
- 觀測：以 Management UI 檢查 ready、unacked、發佈與確認速率

## 步驟
1. 準備環境與設定
2. 建立交換器、佇列與綁定（以設計檔為準）
3. 規劃訊息格式與驗證指標
4. 進行功能驗收與失敗注入
5. 記錄觀測數據與結論

## 設定表（摘要）
| 項目 | 建議 |
|---|---|
| 交換器類型 | 依單元主題 |
| 綁定規則 | 明確列出 pattern 與目標 queue |
| Queue 屬性 | durability、TTL、DLX、優先權 |
| Prefetch | 依工作量與延遲目標設定 |
| 安全 | vhost 隔離與最小權限 |
| 觀測 | 發佈/消費速率、ready/unacked、DLX 速率 |

## 實作重點
- 導出重點參數與取捨理由
- 明確失敗與恢復流程
- 建立可重現的驗收步驟

## 測試
- 正向：訊息正確路由與消費
- 逆向：參數錯誤、佇列不存在、權限不足
- 壓力：持續流量與突刺流量兩種型態

## 觀測
- UI 與指標與預期一致
- 記錄 P50/P95/P99 延遲與吞吐量
- 追蹤 DLQ 與重試率

## 故障演練
- 斷線與重連
- Consumer 宕機
- 訊息過期或拒絕導致 DLQ

## 常見錯誤
- 參數宣告不一致導致建立失敗
- 權限不足
- Prefetch 不當導致飢餓或堆積

## 延伸挑戰
- 加入多租戶 vhost
- 設計更細的 routing key 與監控
- 撰寫實驗報告與調整建議
