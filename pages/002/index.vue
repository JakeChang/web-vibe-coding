<template>
  <div class="bg-gray-100 min-h-screen">
    <!-- Google風格導航條 -->
    <div class="bg-white border-b border-gray-200 py-4 px-6 flex items-center shadow-sm">
      <h1 class="text-xl font-medium text-gray-700">傑克 IT 誌 - Vibe Coding 002 - Google 試算表 API 開發指南</h1>
    </div>
    
    <div class="container mx-auto px-4 py-6 max-w-5xl">
      <!-- 標籤頁導航 -->
      <div class="flex border-b border-gray-200 mb-8">
        <button @click="activeTab = 'principle'" :class="['px-4 py-2 text-sm font-medium focus:outline-none', activeTab === 'principle' ? 'text-blue-600 border-b-2 border-blue-600' : 'text-gray-500 hover:text-gray-700']">
          原理
        </button>
        <button @click="activeTab = 'specification'" :class="['px-4 py-2 text-sm font-medium focus:outline-none', activeTab === 'specification' ? 'text-blue-600 border-b-2 border-blue-600' : 'text-gray-500 hover:text-gray-700']">
          規格撰寫
        </button>
        <button @click="activeTab = 'result'" :class="['px-4 py-2 text-sm font-medium focus:outline-none', activeTab === 'result' ? 'text-blue-600 border-b-2 border-blue-600' : 'text-gray-500 hover:text-gray-700']">
          結果
        </button>
      </div>

      <!-- 內容區 -->
      <div class="bg-white rounded-lg shadow-sm p-6">
        <!-- 原理 -->
        <div v-if="activeTab === 'principle'" class="animate-fade-in">
          <h2 class="text-2xl font-medium text-gray-800 mb-4">Vibe Coding 002 - 使用 Google 試算表製作 API</h2>
          
          <div class="mb-6 bg-blue-50 border-l-4 border-blue-400 p-4">
            <p class="text-blue-700">Google 試算表可以通過 Apps Script 功能製作成簡易的伺服器 API，但此方法有一些限制與解決方案。</p>
          </div>
          
          <div class="space-y-6">
            <div class="bg-white rounded-md border border-gray-200 p-4">
              <h3 class="text-lg font-medium text-gray-800 mb-2">CORS 限制問題</h3>
              <ul class="list-disc pl-6 space-y-1 text-gray-600">
                <li>只能使用 GET 方法來實現 API</li>
                <li>若要支援 POST/PUT/DELETE 等 HTTP 方法，會遇到跨域資源共享 (CORS) 問題</li>
                <li>前端應用呼叫這些方法時，會因為 CORS 問題而被阻擋呼叫</li>
              </ul>
            </div>
            
            <div class="bg-white rounded-md border border-gray-200 p-4">
              <h3 class="text-lg font-medium text-gray-800 mb-2">解決方案</h3>
              <ul class="list-disc pl-6 space-y-1 text-gray-600">
                <li>使用 GET 方法 + JSONP (JSON with Padding) 技術來繞過 CORS 限制</li>
                <li>JSONP 原理：將資料包裝在回調函數中，透過動態創建 script 標籤來加載</li>
                <li>即使資料實際上需要使用 POST/PUT 操作，也透過 GET 請求參數來模擬這些操作</li>
              </ul>
            </div>
            
            <div class="bg-white rounded-md border border-gray-200 p-4">
              <h3 class="text-lg font-medium text-gray-800 mb-2">實作方式</h3>
              <ul class="list-disc pl-6 space-y-1 text-gray-600">
                <li>在 URL 中使用 action 參數來指定操作類型（get/post/put）</li>
                <li>使用 callback 參數來指定 JSONP 回調函數名稱</li>
                <li>在 Apps Script 中處理請求並返回包含回調的響應</li>
              </ul>
            </div>
          </div>
          
          <p class="mt-6 text-gray-600">這種方法雖然有所限制，但可讓您使用 Google 試算表作為簡單的數據存儲和 API 服務，無需部署專門的後端服務器。</p>
        </div>

        <!-- 規格撰寫 -->
        <div v-if="activeTab === 'specification'" class="animate-fade-in">
          <h2 class="text-2xl font-medium text-gray-800 mb-4">Google Apps Script 需求</h2>
          
          <div class="mb-6 bg-yellow-50 border-l-4 border-yellow-400 p-4">
            <p class="text-yellow-700">Google Apps Script 需要支援 JSONP 回調和通過查詢參數處理請求</p>
          </div>
          
          <div class="space-y-6">
            <div class="bg-white rounded-md border border-gray-200 p-4">
              <h3 class="text-lg font-medium text-gray-800 mb-2">Google sheet 欄位</h3>
              <p class="text-gray-600 mb-1">表格名稱為「工作表2」</p>
              <p class="text-gray-600">有三個欄位: id, name, age</p>
            </div>
            
            <div class="bg-white rounded-md border border-gray-200 p-4">
              <h3 class="text-lg font-medium text-gray-800 mb-2">功能要求</h3>
              
              <div class="space-y-4 mt-3">
                <div class="pl-4 border-l-2 border-blue-300">
                  <h4 class="font-medium text-gray-700">取得所有資料</h4>
                  <ul class="list-disc pl-6 text-gray-600 text-sm mt-1">
                    <li>action = get</li>
                  </ul>
                </div>
                
                <div class="pl-4 border-l-2 border-green-300">
                  <h4 class="font-medium text-gray-700">新增資料</h4>
                  <ul class="list-disc pl-6 text-gray-600 text-sm mt-1">
                    <li>action = post</li>
                    <li>data = { name, age}</li>
                    <li>新增資料時，id 要自動累加1</li>
                  </ul>
                </div>
                
                <div class="pl-4 border-l-2 border-yellow-300">
                  <h4 class="font-medium text-gray-700">取得單一資料</h4>
                  <ul class="list-disc pl-6 text-gray-600 text-sm mt-1">
                    <li>action = get</li>
                    <li>id = xx</li>
                  </ul>
                </div>
                
                <div class="pl-4 border-l-2 border-red-300">
                  <h4 class="font-medium text-gray-700">修改資料</h4>
                  <ul class="list-disc pl-6 text-gray-600 text-sm mt-1">
                    <li>action = put</li>
                    <li>data = { id, name, age}</li>
                  </ul>
                </div>
              </div>
            </div>
            
            <div class="bg-white rounded-md border border-gray-200 p-4">
              <h3 class="text-lg font-medium text-gray-800 mb-2">實現檔案</h3>
              <ul class="list-disc pl-6 text-gray-600">
                <li>產生程式碼: xxx.gs</li>
                <li>產生測試說明: xxx.md，使用 curl -L 即可</li>
              </ul>
            </div>
          </div>
        </div>

        <!-- 結果 -->
        <div v-if="activeTab === 'result'" class="animate-fade-in">
          <h2 class="text-2xl font-medium text-gray-800 mb-4">實作結果</h2>
          
          <div class="space-y-4">
            <div class="bg-white rounded-md border border-gray-200 p-4 hover:shadow-md transition duration-200">
              <div class="flex items-center text-blue-600">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4" />
                </svg>
                <a href="https://github.com/JakeChang/google-sheet-api" class="hover:underline">程式碼參考連結</a>
              </div>
            </div>
            
            <!-- <div class="bg-white rounded-md border border-gray-200 p-4 hover:shadow-md transition duration-200">
              <div class="flex items-center text-green-600">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 12a9 9 0 01-9 9m9-9a9 9 0 00-9-9m9 9H3m9 9a9 9 0 01-9-9m9 9c1.657 0 3-4.03 3-9s-1.343-9-3-9m0 18c-1.657 0-3-4.03-3-9s1.343-9 3-9m-9 9a9 9 0 019-9" />
                </svg>
                <a href="https://xxx" class="hover:underline">線上 Demo</a>
              </div>
            </div> -->
            
            <div class="bg-white rounded-md border border-gray-200 p-4 hover:shadow-md transition duration-200">
              <div class="flex items-center text-red-600">
                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 10l4.553-2.276A1 1 0 0121 8.618v6.764a1 1 0 01-1.447.894L15 14M5 18h8a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v8a2 2 0 002 2z" />
                </svg>
                <a href="https://youtu.be/8HBgF0q3L0c" class="hover:underline">Youtube 講解</a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    
    <!-- Footer -->
    <div class="bg-white border-t border-gray-200 py-4 mt-8">
      <div class="container mx-auto px-4 text-center text-gray-500 text-sm">
        <p>傑克 IT 誌 - Vibe Coding 002</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const activeTab = ref('principle');
</script>

<style>
.animate-fade-in {
  animation: fadeIn 0.3s ease-in-out;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>