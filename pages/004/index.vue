<template>
  <div class="min-h-screen bg-amber-50 py-10 px-4 md:px-8">
    <div class="max-w-3xl mx-auto bg-white rounded-lg shadow-lg overflow-hidden border-t-8 border-yellow-400">
      <!-- 筆記本風格頁面 -->
      <div class="p-6 md:p-8">
        <!-- 頁面標題 -->
        <h1 class="text-3xl font-bold text-gray-800 mb-6 border-b pb-4">Vibe Coding 004</h1>
        
        <!-- 內容區 -->
        <div class="prose prose-slate max-w-none notebook-content">
          <h2 class="text-2xl font-bold mt-6 mb-4">Nuxt 製作一個購買物品紀錄系統</h2>
          
          <h3 class="text-xl font-bold mt-5 mb-3">Google Sheet API 規格</h3>
          <p>使用 Google Sheet 來製作 API，撰寫 spec:</p>
          
          <div class="bg-gray-50 p-4 rounded-lg my-4 border-l-4 border-gray-300">
            <h4 class="font-bold">Google Apps Script 需求</h4>
            <p>Google Apps Script 需要支援 JSONP 回調和通過查詢參數處理請求</p>
            
            <h4 class="font-bold mt-4">Google sheet 欄位</h4>
            <ul class="list-disc pl-5 mt-2">
              <li>表格名稱為「工作表1」</li>
              <li>有五個欄位:</li>
              <ul class="list-disc pl-5">
                <li>id: 整數</li>
                <li>name: 字串</li>
                <li>buy_date: 日期</li>
                <li>warranty_period: 數字(天)</li>
                <li>warranty_date: 日期</li>
              </ul>
            </ul>
            
            <h4 class="font-bold mt-4">功能要求</h4>
            <p>必須要生成以下四個 API，並且 doGet 與 doPost 都是用 JSONP 參數來處理請求</p>
            <ul class="list-disc pl-5 mt-2">
              <li>取得所有資料
                <ul class="list-disc pl-5">
                  <li>action = get</li>
                </ul>
              </li>
              <li>新增資料
                <ul class="list-disc pl-5">
                  <li>action = post</li>
                  <li>data = { name, buy_date, warranty_period }</li>
                  <li>新增資料時，id 要自動累加 1</li>
                  <li>新增資料時，warranty_date 會等於 buy_date 加上 warranty_period(天數)</li>
                </ul>
              </li>
              <li>取得單一資料
                <ul class="list-disc pl-5">
                  <li>action = get</li>
                  <li>id = xx</li>
                </ul>
              </li>
              <li>修改資料
                <ul class="list-disc pl-5">
                  <li>action = put</li>
                  <li>data = { id, name, buy_date, warranty_period }</li>
                  <li>修改資料時，warranty_date 會等於 buy_date 加上 warranty_period(天數)</li>
                </ul>
              </li>
            </ul>
            
            <h4 class="font-bold mt-4">實現檔案</h4>
            <ul class="list-disc pl-5 mt-2">
              <li>產生程式碼: xxx.gs</li>
              <li>產生測試說明: xxx.md，使用 curl -L 即可，必須要用 --data-urlencode 編碼</li>
            </ul>
          </div>
          
          <h3 class="text-xl font-bold mt-5 mb-3">Web 規格</h3>
          <p>使用 Nuxt 框架來製作 API，詳細的專案建立可以參考 001: pages/001</p>
          <p>撰寫 spec:</p>
          
          <div class="bg-gray-50 p-4 rounded-lg my-4 border-l-4 border-gray-300">
            <h4 class="font-bold">頁面結構</h4>
            <p>實現一個簡單的購買物品紀錄</p>
            
            <h4 class="font-bold mt-4">功能要求</h4>
            <ul class="list-disc pl-5 mt-2">
              <li>列表: 用列表方式顯示，頁面讀取時，需要有 loading 狀態
                <ul class="list-disc pl-5">
                  <li>在列表頁面上方新增一個 summary 區塊</li>
                  <li>列出最近 30 天快要到期的物品，使用 warranty_date 來判斷</li>
                </ul>
              </li>
              <li>新增: 用表單方式建立</li>
              <li>修改: 用表單方式修改資料，與新增共用頁面</li>
            </ul>
            
            <h4 class="font-bold mt-4">欄位要求</h4>
            <ul class="list-disc pl-5 mt-2">
              <li>取得所有: id,name,buy_date,warranty_period,warranty_date,按鈕(編輯)</li>
              <li>建立單筆: name,buy_date(日期),warranty_period(天數，用數字表示)</li>
              <li>更新單筆: name,buy_date(日期),warranty_period(天數，用數字表示)</li>
            </ul>
            
            <h4 class="font-bold mt-4">實現檔案</h4>
            <ul class="list-disc pl-5 mt-2">
              <li>主頁面元件:</li>
              <ul class="list-disc pl-5">
                <li>pages/demo/index.vue: 呈現列表資料的頁面</li>
                <li>pages/demo/add.vue: 新增與修改資料的頁面，如果網址有帶入 id，則為修改，要先去取得單一資料。</li>
              </ul>
              <li>邏輯處理: composables/useDemo.ts</li>
              <ul class="list-disc pl-5">
                <li>負責邏輯，管理 UI 狀態</li>
                <li>處理錯誤訊息</li>
                <li>處理表單驗證邏輯</li>
                <li>提供表單提交方法</li>
                <li>管理 UI 狀態</li>
              </ul>
              <li>API 呼叫: utils/demoService.ts</li>
              <ul class="list-disc pl-5">
                <li>服務層，負責 API 串接</li>
                <li>使用 JSONP 方式處理 POST/PUT 請求，繞過 CORS 限制</li>
                <li>提供錯誤處理</li>
              </ul>
            </ul>
            
            <h4 class="font-bold mt-4">API</h4>
            <p>取得所有資料:</p>
            <pre class="bg-gray-800 text-white p-3 rounded text-sm overflow-x-auto">curl -L --get \
  --data-urlencode "action=get" \
  --data-urlencode "callback=handleResponse" \
  "https://script.google.com/macros/s/AKfycbwFcSx8zMYcKdnwqdfauch2buFgwgdPq4NR4Q9QTmXXSoevUKCsin7S2WWqTGhE2cu_nA/exec"

handleResponse({"success":true,"data":[{"id":1,"name":"高效能筆記型電腦","buy_date":"2023-01-15T00:00:00.000Z","warranty_period":730,"warranty_date":"2025-01-14T00:00:00.000Z"}]})</pre>
            
            <p class="mt-4">取得單一資料:</p>
            <pre class="bg-gray-800 text-white p-3 rounded text-sm overflow-x-auto">curl -L --get \
  --data-urlencode "action=get" \
  --data-urlencode "id=1" \
  --data-urlencode "callback=handleResponse" \
  "https://script.google.com/macros/s/AKfycbwFcSx8zMYcKdnwqdfauch2buFgwgdPq4NR4Q9QTmXXSoevUKCsin7S2WWqTGhE2cu_nA/exec"

handleResponse({"success":true,"data":{"id":1,"name":"高效能筆記型電腦","buy_date":"2023-01-15T00:00:00.000Z","warranty_period":730,"warranty_date":"2025-01-14T00:00:00.000Z"}})</pre>
            
            <p class="mt-4">新增 (通過 JSONP 實現):</p>
            <pre class="bg-gray-800 text-white p-3 rounded text-sm overflow-x-auto">curl -L --get \
  --data-urlencode "action=post" \
  --data-urlencode 'data={"name":"筆記型電腦","buy_date":"2023-01-15","warranty_period":365}' \
  --data-urlencode "callback=handleResponse" \
  "https://script.google.com/macros/s/AKfycbwFcSx8zMYcKdnwqdfauch2buFgwgdPq4NR4Q9QTmXXSoevUKCsin7S2WWqTGhE2cu_nA/exec"

handleResponse({"success":true,"data":{"id":2,"name":"筆記型電腦","buy_date":"2023-01-15T00:00:00.000Z","warranty_period":365,"warranty_date":"2024-01-15T00:00:00.000Z"}})</pre>
            
            <p class="mt-4">修改 (通過 JSONP 實現):</p>
            <pre class="bg-gray-800 text-white p-3 rounded text-sm overflow-x-auto">curl -L --get \
  --data-urlencode "action=put" \
  --data-urlencode 'data={"id":1,"name":"高效能筆記型電腦","buy_date":"2023-01-15","warranty_period":730}' \
  --data-urlencode "callback=handleResponse" \
  "https://script.google.com/macros/s/AKfycbwFcSx8zMYcKdnwqdfauch2buFgwgdPq4NR4Q9QTmXXSoevUKCsin7S2WWqTGhE2cu_nA/exec"

handleResponse({"success":true,"data":{"id":1,"name":"高效能筆記型電腦","buy_date":"2023-01-15T00:00:00.000Z","warranty_period":730,"warranty_date":"2025-01-14T00:00:00.000Z"}})</pre>
            
            <h4 class="font-bold mt-4">備註</h4>
            <ul class="list-disc pl-5 mt-2">
              <li>使用 tailwindcss 排版</li>
              <li>應用 JSONP 技術繞過 CORS 限制，不依賴伺服器代理</li>
            </ul>
          </div>
          
          <h3 class="text-xl font-bold mt-5 mb-3">結果</h3>
          <ul class="list-disc pl-5 mt-2">
            <li>程式碼: 可以在 <a href="https://github.com/JakeChang/vibe004-web-buy" class="text-blue-600 hover:underline">https://github.com/JakeChang/vibe004-web-buy</a> 參考相關程式碼</li>
            <li>線上 Demo: <a href="https://jk-vibe004.netlify.app/" class="text-blue-600 hover:underline">https://jk-vibe004.netlify.app/</a></li>
            <li>youtube 講解: <a href="https://www.youtube.com/watch?v=xxx" class="text-blue-600 hover:underline">https://www.youtube.com/watch?v=xxx</a></li>
          </ul>
        </div>
      </div>
      
      <!-- 筆記本底部裝飾 -->
      <div class="h-4 bg-yellow-400"></div>
    </div>
  </div>
</template>

<script setup>
// 沒有需要額外的腳本，只需呈現 HTML 內容
</script>

<style>
.notebook-content h2, .notebook-content h3, .notebook-content h4 {
  font-family: 'Courier New', Courier, monospace;
  position: relative;
}

.notebook-content h2::before, .notebook-content h3::before {
  content: "📝";
  margin-right: 0.5rem;
}

.notebook-content pre {
  border-left: 4px solid #3b82f6;
}

.notebook-content a {
  text-decoration: underline;
  color: #3b82f6;
}
</style> 