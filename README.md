# SkyBound Interface

### 🚀 現代化無人物流與自主導航監控平台

**SkyBound OS** 是一套基於 Web 技術的開源無人機/物流車監控系統。它旨在提供高併發、低延遲的即時遙測數據，結合機械人視覺與地圖路徑規劃，讓開發者能透過瀏覽器完整監控自主移動機器人 (AMR)。

---

## 🛠 技術堆疊 (VibeStack+)

我們採用極致效能的技術組合，確保在高資料量下依然流暢：

* **建構工具**: [Rspack](https://www.rspack.dev/) (閃電般的編譯速度)
* **前端框架**: [Solid.js](https://www.solidjs.com/) (輕量、高效的反應式渲染)
* **地圖引擎**: [MapLibre GL JS](https://maplibre.org/) 或 [Deck.gl](https://deck.gl/) (高效能數據可視化)
* **數據通訊**: WebSockets / WebRTC (用於即時視覺串流)
* **狀態管理**: Solid Stores
* **型別安全**: ArkType (用於感測器資料驗證)

---

## 🏗 功能特點

* **即時地圖系統**: 整合 GIS 數據，即時繪製起點、終點及動態路徑。
* **視覺遙測**: 透過 WebRTC 直接在瀏覽器顯示機器人機載鏡頭畫面。
* **狀態監控儀表板**:
* **電量 (SoC)**: 精確的電壓與剩餘續航顯示。
* **機械狀態**: 馬達轉速、溫度、姿態角度 (IMU)。
* **系統負載**: 當前 CPU/RAM 使用率。


* **任務管理**: 遠端下達導航目標點，即時更新路徑規劃。

---

## 📂 專案結構

```text
├── src/
│   ├── components/      # UI 組件 (Dashboard, Map, Status Cards)
│   ├── hooks/           # WebRTC/Socket 狀態處理
│   ├── store/           # 機器人狀態管理
│   ├── assets/          # 視覺資源與圖標
│   └── utils/           # 座標轉換與通訊協定處理
├── public/
├── rspack.config.mjs    # Rspack 配置
└── package.json

```

---

## 🚀 快速開始

### 前置需求

* Node.js >= 20.0.0
* 支援 WebSocket 的後端數據源 (例如 ROS2 bridge 或自定義 MQTT)

### 安裝與運行

```bash
# 複製專案
git clone https://github.com/your-username/skybound-os.git

# 安裝依賴
npm install

# 啟動開發模式
npm run dev

```

---

## 🤖 機器人通訊協議 (範例)

本專案預設使用 JSON 結構進行狀態同步，確保與 PostgreSQL 後端的高度整合：

```json
{
  "robot_id": "AMR-001",
  "status": "navigating",
  "battery": 88,
  "position": { "lat": 22.3193, "lng": 114.1694 },
  "telemetry": {
    "velocity": 1.2,
    "temperature": 45
  },
  "timestamp": "2026-07-15T10:09:57Z"
}

```

---

## 💡 開發計劃

* [ ] **Phase 1**: 建立 Rspack 基礎環境並導入 Solid.js。
* [ ] **Phase 2**: 完成 MapLibre 地圖渲染與座標點對應功能。
* [ ] **Phase 3**: 整合 WebRTC 視覺串流通道。
* [ ] **Phase 4**: 實現實時數據 Store 並與後端 API 連結。
* [ ] **Phase 5**: 優化高併發狀態下的渲染效能 (Web Workers 應用)。

---

## 🤝 貢獻

我們歡迎任何關於自主導航與前端高效能開發的貢獻。請先閱讀 [CONTRIBUTING.md](https://www.google.com/search?q=CONTRIBUTING.md)。

## 📄 授權

MIT License
