# RabbitMQ 技術研究教程

目的：提供從入門到進階的學習路線與小型 POC 規格。每個單元為獨立目錄，包含 `README.md`、`design.md` 與範例程式碼。

## 學習順序
00-setup-and-basics → 01-hello-queue → 02-exchanges-and-bindings → 03-durability-and-persistence → 04-ack-qos-prefetch → 05-publisher-confirms-vs-transactions → 06-dlx-and-ttl → 07-retry-policies-and-backoff → 08-idempotent-consumers → 09-transactional-outbox → 10-rpc-over-rabbitmq → 11-priority-and-delayed-messages → 12-quorum-vs-classic-mirrored → 13-connection-resiliency → 14-security-auth-tls-vhost-policy → 15-observability-and-metrics → 16-performance-tuning → 17-integration-with-web-api → 18-saga-and-process-orchestration → 99-poc-high-concurrency-reservation

## 全域規範
- 說明語言：繁體中文
- 產出：每單元 `README.md`、`design.md`
- 風格：以「為何、如何、如何驗證、失敗如何排錯」撰寫
- 可靠性語意：at-most-once / at-least-once / exactly-once 以設計角度說明
- 觀測：以 Management UI 與指標清單對照驗證

## 目錄結構
- `docs/`：共用參考文件
- `NN-topic/`：單元資料夾（NN 為 2 位數序號）
  - `README.md`：學習說明與任務
  - `design.md`：架構與參數設計
  - `code/`：對應主題的示範程式碼

## 版本與時間
- 版本：v1.0
- 生成時間：2025-08-12 17:12 UTC
