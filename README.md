# Lawundry - 維護頁面

此資料夾包含 Lawundry 網站的靜態維護頁面，用於部署在 GitHub Pages。

## 檔案結構

```
UnderMaintenancePage/
├── index.html      # 主頁面
├── style.css       # 樣式表
├── favicon.ico     # 網站圖標
└── README.md       # 本說明文件
```

## 部署至 GitHub Pages

### 方法一：使用此資料夾作為 gh-pages 分支

1. 建立新的 orphan 分支：
   ```bash
   git checkout --orphan gh-pages
   ```

2. 清除所有檔案：
   ```bash
   git rm -rf .
   ```

3. 複製維護頁面檔案到根目錄：
   ```bash
   cp UnderMaintenancePage/* .
   ```

4. 提交並推送：
   ```bash
   git add .
   git commit -m "Deploy maintenance page"
   git push origin gh-pages
   ```

### 方法二：使用 GitHub Actions 自動部署

在 `.github/workflows/` 建立部署工作流程。

### 方法三：直接設定 GitHub Pages

1. 前往 Repository Settings > Pages
2. Source 選擇 `Deploy from a branch`
3. Branch 選擇 `main`，資料夾選擇 `/UnderMaintenancePage`

## 自訂內容

### 修改聯絡資訊

編輯 `index.html` 中的聯絡區塊：

```html
<div class="contact-section">
    <h3 class="contact-title">聯絡資訊</h3>
    <div class="contact-item">
        <span class="contact-label">GitHub</span>
        <a href="YOUR_GITHUB_URL">YOUR_GITHUB_URL</a>
    </div>
    <!-- 可新增更多聯絡方式 -->
</div>
```

### 修改 Canva 簡報

更換 `index.html` 中的 iframe src：

```html
<iframe 
    src="YOUR_CANVA_EMBED_URL"
    allowfullscreen="allowfullscreen" 
    allow="fullscreen">
</iframe>
```

## 特色

- 響應式設計（支援桌面、平板、手機）
- 不可滾動的單頁設計
- 黃黑配色主題
- 嵌入 Canva 簡報
- 純靜態 HTML/CSS，無需伺服器

## 瀏覽器支援

- Chrome (最新版)
- Firefox (最新版)
- Safari (最新版)
- Edge (最新版)
- 行動裝置瀏覽器
