# Google Analytics 4 設置說明

## 概述
本專案已整合 Google Analytics 4 (GA4) 追蹤代碼，用於分析用戶行為和網站使用情況。

## 設置步驟

### 1. 創建 GA4 帳戶
1. 前往 [Google Analytics](https://analytics.google.com/)
2. 點擊「開始評估」
3. 創建帳戶和資料串流
4. 選擇「網站」作為平台

### 2. 獲取追蹤 ID
1. 在資料串流設定中找到「測量 ID」
2. 格式為：`G-XXXXXXXXXX`
3. 複製此 ID

### 3. 更新追蹤代碼
在 `index.html` 文件中，將以下代碼中的 `G-XXXXXXXXXX` 替換為您的實際測量 ID：

```html
<!-- Google Analytics 4 -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
    window.dataLayer = window.dataLayer || [];
    function gtag(){dataLayer.push(arguments);}
    gtag('js', new Date());
    gtag('config', 'G-XXXXXXXXXX', {
        page_title: '核三重啟議題互動分析儀表板',
        page_location: window.location.href,
        custom_map: {
            'custom_parameter_1': 'page_section',
            'custom_parameter_2': 'user_interaction'
        }
    });
</script>
```

## 追蹤功能

### 自動追蹤
- **頁面瀏覽**：每次頁面載入
- **頁面載入完成**：頁面完全載入後觸發

### 自定義事件追蹤

#### 1. 導航互動
- **事件名稱**：`navigation_click`
- **觸發條件**：點擊導航連結
- **追蹤數據**：目標區段、導航類型

#### 2. 內容互動
- **事件名稱**：`card_interaction`
- **觸發條件**：點擊正反論點卡片
- **追蹤數據**：卡片標題、論點類型（正面/反面）、動作（展開/收合）

#### 3. 滾動深度
- **事件名稱**：`scroll_depth`
- **觸發條件**：滾動到 25%、50%、75%、100% 等里程碑
- **追蹤數據**：滾動百分比

#### 4. 圖表互動
- **事件名稱**：`chart_interaction`
- **觸發條件**：點擊成本比較圖或碳排放圖
- **追蹤數據**：圖表類型、互動類型

#### 5. 移動端選單
- **事件名稱**：`mobile_menu_toggle`
- **觸發條件**：開啟/關閉移動端選單
- **追蹤數據**：選單狀態

## 自定義參數

每個事件都包含以下自定義參數：
- `custom_parameter_1`：頁面區段或內容類型
- `custom_parameter_2`：用戶互動類型

## 數據分析

### 在 GA4 中查看數據
1. **即時報告**：查看當前活躍用戶
2. **事件報告**：分析用戶互動模式
3. **參與度報告**：了解頁面瀏覽和停留時間
4. **轉換報告**：設定和追蹤目標完成

### 建議的轉換目標
- 頁面瀏覽（100% 滾動）
- 卡片互動（內容參與）
- 圖表互動（數據探索）
- 導航使用（網站導航）

## 隱私合規

### 必要的隱私政策更新
請確保您的隱私政策包含：
- Google Analytics 使用說明
- Cookie 使用說明
- 數據收集目的說明
- 用戶選擇退出選項

### GDPR 合規
- 提供明確的同意機制
- 允許用戶選擇退出追蹤
- 提供數據刪除選項

## 故障排除

### 常見問題
1. **追蹤代碼未載入**：檢查網路連接和腳本載入
2. **事件未觸發**：檢查瀏覽器控制台錯誤
3. **數據延遲**：GA4 數據通常有 24-48 小時延遲

### 測試工具
- **Google Tag Assistant**：Chrome 擴展
- **GA4 DebugView**：即時事件測試
- **瀏覽器開發者工具**：檢查網路請求和錯誤

## 維護建議

### 定期檢查
- 每月檢查事件觸發情況
- 季度審查追蹤目標和轉換
- 年度更新隱私政策和追蹤設置

### 性能優化
- 監控頁面載入速度
- 優化追蹤代碼載入
- 減少不必要的追蹤事件

## 聯繫支持

如有技術問題，請參考：
- [Google Analytics 幫助中心](https://support.google.com/analytics/)
- [GA4 開發者文檔](https://developers.google.com/analytics/devguides/collection/ga4)
- [Google Analytics 社群論壇](https://support.google.com/analytics/community)
