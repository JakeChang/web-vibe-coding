<template>
  <div class="min-h-screen bg-amber-50 py-8 px-4 sm:px-6 lg:px-8">
    <div class="max-w-4xl mx-auto">
      <div class="bg-white shadow-lg rounded-lg overflow-hidden">
        <!-- 筆記本風格頁面 -->
        <div class="border-b border-gray-200 p-6 bg-red-100">
          <h1 class="text-3xl font-bold text-gray-900">傑克 IT 誌 - Vibe Coding</h1>
        </div>
        
        <!-- 筆記內容區 -->
        <div class="p-6 notebook-content">
          <div v-html="htmlContent" class="prose prose-slate max-w-none"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const htmlContent = `
<h1>Vibe Coding 003</h1>
<p>Nuxt.js 串接 Google Sheet API</p>

<h2>準備 API</h2>
<p>使用 Vibe Coding 002 所產生的 API 來串接，會產生以下四隻API，此為範例表示:</p>

<ul>
  <li>
    <p>取得所有資料:</p>
    <pre><code>curl -L "https://script.google.com/macros/s/{key}/exec?action=get&callback=myCallback"

myCallback({"success":true,"data":[{"id":1,"name":"張三","age":25}],"error":null})%</code></pre>
  </li>
  
  <li>
    <p>取得單一資料:</p>
    <pre><code>curl -L "https://script.google.com/macros/s/{key}/exec?action=get&id=1&callback=myCallback"

myCallback({"success":true,"data":{"id":1,"name":"張三","age":25},"error":null})%</code></pre>
  </li>
  
  <li>
    <p>新增 (通過 JSONP 實現):</p>
    <pre><code>curl -L "https://script.google.com/macros/s/{key}/exec?action=post" --data-urlencode "data={\"name\":\"張三\",\"age\":25}" --data-urlencode "callback=myCallback" -G

myCallback({"success":true,"data":{"id":2,"name":"張三","age":25},"error":null})%</code></pre>
  </li>
  
  <li>
    <p>修改 (通過 JSONP 實現):</p>
    <pre><code>curl -L "https://script.google.com/macros/s/{key}/exec?action=put" --data-urlencode "data={\"id\":1,\"name\":\"李四\",\"age\":30}" --data-urlencode "callback=myCallback" -G

myCallback({"success":true,"data":{"id":1,"name":"李四","age":30},"error":null})%</code></pre>
  </li>
</ul>

<h2>規格撰寫</h2>
<pre><code># 頁面結構

實現新增、列表、修改資料的功能

## 功能要求

- 列表: 用列表方式顯示，頁面讀取時，需要有 loading 狀態
- 新增: 用表單方式建立
- 修改: 用表單方式修改資料，與新增共用頁面

## 欄位要求

- 取得所有: id,name,age,按鈕(編輯)
- 建立單筆: name,age
- 更新單筆: name,age

## 實現檔案

- 主頁面元件: 
    - pages/demo/index.vue: 呈現列表資料的頁面
    - pages/demo/add.vue: 新增與修改資料的頁面，如果網址有帶入 id，則為修改，要先去取得單一資料。
- 邏輯處理: composables/useDemo.ts
    - 負責邏輯，管理 UI 狀態
    - 處理錯誤訊息
    - 處理表單驗證邏輯
    - 提供表單提交方法
    - 管理 UI 狀態
- API 呼叫: utils/demoService.ts
    - 服務層，負責 API 串接
    - 使用 JSONP 方式處理 POST/PUT 請求，繞過 CORS 限制
    - 提供錯誤處理

## API

- 取得所有資料:

    \`\`\`
    curl -L "https://script.google.com/macros/s/AKfycbxVzNySL1Y1-cX68CkUQwIxd3_GbTq4xYcLX_kt1deaiqUryOe-35fRm66hcWOsV5dc/exec?action=get&callback=myCallback"

    myCallback({"success":true,"data":[{"id":1,"name":"張三","age":25}],"error":null})% 
    \`\`\`

- 取得單一資料:

    \`\`\`
    curl -L "https://script.google.com/macros/s/AKfycbxVzNySL1Y1-cX68CkUQwIxd3_GbTq4xYcLX_kt1deaiqUryOe-35fRm66hcWOsV5dc/exec?action=get&id=1&callback=myCallback"

    myCallback({"success":true,"data":{"id":1,"name":"張三","age":25},"error":null})% 
    \`\`\`

- 新增 (通過 JSONP 實現):

    \`\`\`
    curl -L "https://script.google.com/macros/s/AKfycbxVzNySL1Y1-cX68CkUQwIxd3_GbTq4xYcLX_kt1deaiqUryOe-35fRm66hcWOsV5dc/exec?action=post" --data-urlencode "data={\"name\":\"張三\",\"age\":25}" --data-urlencode "callback=myCallback" -G

    myCallback({"success":true,"data":{"id":2,"name":"張三","age":25},"error":null})% 
    \`\`\`

- 修改 (通過 JSONP 實現):

    \`\`\`
    curl -L "https://script.google.com/macros/s/AKfycbxVzNySL1Y1-cX68CkUQwIxd3_GbTq4xYcLX_kt1deaiqUryOe-35fRm66hcWOsV5dc/exec?action=put" --data-urlencode "data={\"id\":1,\"name\":\"李四\",\"age\":30}" --data-urlencode "callback=myCallback" -G

    myCallback({"success":true,"data":{"id":1,"name":"李四","age":30},"error":null})% 
    \`\`\`

## 備註

- 使用 tailwindcss 排版
- 應用 JSONP 技術繞過 CORS 限制，不依賴伺服器代理</code></pre>

<h2>結果</h2>
<ul>
  <li>程式碼: 可以在 <a href="https://github.com/JakeChang/vibe003-web-googlesheet" target="_blank">https://github.com/JakeChang/vibe003-web-googlesheet</a> 參考相關程式碼</li>
  <li>線上 Demo: <a href="https://jk-vibe003.netlify.app/" target="_blank">https://jk-vibe003.netlify.app/</a></li>
  <li>youtube 講解: <a href="https://youtu.be/IM2z4qFcxsE" target="_blank">https://youtu.be/IM2z4qFcxsE</a></li>
</ul>
`
</script>

<style scoped>
.notebook-content {
  position: relative;
  line-height: 1.6;
  font-family: 'PT Serif', serif;
  background-image: linear-gradient(#f1f5f9 1px, transparent 1px);
  background-size: 100% 2rem;
  padding-top: 0.5rem;
}

.notebook-content :deep(pre) {
  background-color: #f8fafc;
  border-radius: 0.375rem;
  padding: 1rem;
  border: 1px solid #e2e8f0;
  margin: 1rem 0;
  overflow-x: auto;
}

.notebook-content :deep(h1) {
  color: #1e293b;
  font-size: 2rem;
  font-weight: 700;
  margin-bottom: 1.5rem;
  padding-bottom: 0.5rem;
  border-bottom: 2px solid #e2e8f0;
}

.notebook-content :deep(h2) {
  color: #334155;
  font-size: 1.5rem;
  font-weight: 600;
  margin-top: 1.5rem;
  margin-bottom: 1rem;
  border-bottom: 1px solid #e2e8f0;
  padding-bottom: 0.25rem;
}

.notebook-content :deep(ul) {
  padding-left: 1.5rem;
  margin: 1rem 0;
}

.notebook-content :deep(li) {
  margin-bottom: 0.5rem;
}

.notebook-content :deep(p) {
  margin-bottom: 1rem;
}

.notebook-content :deep(code) {
  font-family: 'Fira Code', monospace;
  font-size: 0.9rem;
}
</style> 