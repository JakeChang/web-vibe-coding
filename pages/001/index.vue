<template>
  <div class="min-h-screen bg-black text-green-500 font-mono p-8 overflow-auto">
    <div class="container mx-auto">
      <article class="border border-green-500 p-6 shadow-lg shadow-green-500/20">
        <div class="mb-6 border-b border-green-500 pb-4">
          <div class="flex items-center mb-2">
            <span class="text-green-700 mr-2">[系統]</span>
            <span class="text-green-400 animate-pulse">連接成功...</span>
          </div>
          <h1 class="text-3xl font-bold glitch-text mb-2">Vibe Coding 001</h1>
          <p class="text-green-400">使用 Vue + Nuxt 製作酷炫 blog</p>
        </div>
        
        <div class="terminal-section mb-8">
          <div class="flex items-center mb-3">
            <span class="text-green-700 mr-2">[root@vibeserver]#</span>
            <span class="text-green-300">cat 專案建立.txt</span>
          </div>
          <h2 class="text-2xl font-bold text-green-300 border-l-4 border-green-500 pl-3 mb-4">專案建立</h2>
          <p class="mb-2 text-green-400">建立一個 Nuxt 專案:</p>
          <pre class="bg-gray-900 p-4 border border-green-700 mb-4 overflow-x-auto text-green-400"><code>npx nuxi init my-nuxt-app</code></pre>
          
          <p class="mb-2 text-green-400">安裝相關套件:</p>
          <pre class="bg-gray-900 p-4 border border-green-700 mb-4 overflow-x-auto text-green-400"><code>cd my-nuxt-app
npm install</code></pre>
          
          <p class="mb-2 text-green-400">啟動專案:</p>
          <pre class="bg-gray-900 p-4 border border-green-700 mb-4 overflow-x-auto text-green-400"><code>npm run dev</code></pre>
          
          <p class="mb-2 text-green-400">即可在瀏覽器開啟 <code class="text-green-300">http://localhost:3000</code></p>
        </div>
        
        <div class="terminal-section mb-8">
          <div class="flex items-center mb-3">
            <span class="text-green-700 mr-2">[root@vibeserver]#</span>
            <span class="text-green-300">cat tailwind安裝.txt</span>
          </div>
          <h2 class="text-2xl font-bold text-green-300 border-l-4 border-green-500 pl-3 mb-4">安裝 tailwindcss 套件</h2>
          <p class="mb-2 text-green-400">安裝 tailwindcss 4 套件:</p>
          <pre class="bg-gray-900 p-4 border border-green-700 mb-4 overflow-x-auto text-green-400"><code>npm install tailwindcss @tailwindcss/vite</code></pre>
          
          <p class="mb-2 text-green-400">在專案的 nuxt.config.ts 修改為:</p>
          <pre class="bg-gray-900 p-4 border border-green-700 mb-4 overflow-x-auto text-green-400"><code>import tailwindcss from '@tailwindcss/vite'

export default defineNuxtConfig({
  compatibilityDate: '2024-11-01',
  devtools: { enabled: true },
  vite: {
    plugins: [
      tailwindcss(),
    ]
  },
  css: ['~/assets/css/main.css']
})</code></pre>
          
          <p class="mb-2 text-green-400">新增 assets/css/main.css 檔案:</p>
          <pre class="bg-gray-900 p-4 border border-green-700 mb-4 overflow-x-auto text-green-400"><code>@import "tailwindcss";</code></pre>
          
          <p class="mb-2 text-green-400">可以在 app.vue 測試是否安裝成功:</p>
          <pre class="bg-gray-900 p-4 border border-green-700 mb-4 overflow-x-auto text-green-400"><code>&lt;h1 class="text-3xl font-bold underline"&gt;
    Hello world!
&lt;/h1&gt;</code></pre>
        </div>
        
        <div class="terminal-section mb-8">
          <div class="flex items-center mb-3">
            <span class="text-green-700 mr-2">[root@vibeserver]#</span>
            <span class="text-green-300">cat 調整結構.txt</span>
          </div>
          <h2 class="text-2xl font-bold text-green-300 border-l-4 border-green-500 pl-3 mb-4">調整結構</h2>
          <p class="mb-2 text-green-400">app.vue</p>
          <pre class="bg-gray-900 p-4 border border-green-700 mb-4 overflow-x-auto text-green-400"><code>&lt;template&gt;
  &lt;div&gt;
    &lt;NuxtPage /&gt;
  &lt;/div&gt;
&lt;/template&gt;</code></pre>
          
          <p class="mb-2 text-green-400">pages/index.vue</p>
          <pre class="bg-gray-900 p-4 border border-green-700 mb-4 overflow-x-auto text-green-400"><code>&lt;template&gt;
  &lt;div&gt;
    &lt;h1&gt;Welcome to your Nuxt Application&lt;/h1&gt;
  &lt;/div&gt;
&lt;/template&gt;</code></pre>
        </div>
        
        <div class="terminal-section mb-8">
          <div class="flex items-center mb-3">
            <span class="text-green-700 mr-2">[root@vibeserver]#</span>
            <span class="text-green-300">cat 規格撰寫.txt</span>
          </div>
          <h2 class="text-2xl font-bold text-green-300 border-l-4 border-green-500 pl-3 mb-4">規格撰寫</h2>
          <p class="mb-2 text-green-400">新增一個 spec.md，加入規格:</p>
          <pre class="bg-gray-900 p-4 border border-green-700 mb-4 overflow-x-auto text-green-400"><code># 頁面結構

技術文件部落格

## 功能要求

可以瀏覽技術文件

## 實現檔案

- 主頁面元件: pages/001/index.vue
    - 將 pages/001/001.md 所有內容直接轉換成 html，呈現在頁面上
    - 不需要使用 md 套件，請直接轉成 html 即可

## 備註

- 使用 tailwindcss 排版</code></pre>
          
          <p class="mb-2 text-green-400">Prompt指令:</p>
          <pre class="bg-gray-900 p-4 border border-green-700 mb-4 overflow-x-auto text-green-400"><code>根據 spec.md 的規格內容產生對應程式碼即可</code></pre>
        </div>
        
        <div class="terminal-section">
          <div class="flex items-center mb-3">
            <span class="text-green-700 mr-2">[root@vibeserver]#</span>
            <span class="text-green-300">cat 結果.txt</span>
          </div>
          <h3 class="text-xl font-bold text-green-300 border-l-4 border-green-500 pl-3 mb-3">結果</h3>
          <ul class="list-none pl-6 mb-4">
            <li class="mb-2 flex items-center">
              <span class="text-green-700 mr-2">[>]</span>
              <span class="text-green-400">程式碼: 可以在 <a href="https://xxx" class="text-green-300 underline hover:text-green-100">https://xxx</a> 參考相關程式碼</span>
            </li>
            <li class="mb-2 flex items-center">
              <span class="text-green-700 mr-2">[>]</span>
              <span class="text-green-400">線上 Demo: <a href="https://xxx" class="text-green-300 underline hover:text-green-100">https://xxx</a></span>
            </li>
            <li class="mb-2 flex items-center">
              <span class="text-green-700 mr-2">[>]</span>
              <span class="text-green-400">youtube 講解: <a href="https://xxx" class="text-green-300 underline hover:text-green-100">https://xxx</a></span>
            </li>
          </ul>
        </div>
        
        <div class="border-t border-green-500 pt-4 mt-8">
          <div class="flex items-center">
            <span class="text-green-700 mr-2">[系統]</span>
            <span class="text-green-400 animate-pulse">連線即將中斷...</span>
          </div>
        </div>
      </article>
    </div>
  </div>
</template>

<script setup>
// 不需使用 md 套件，直接以 HTML 呈現 001.md 內容
</script>

<style scoped>
.glitch-text {
  position: relative;
  animation: glitch 3s infinite;
}

@keyframes glitch {
  0% { text-shadow: 0.05em 0 0 rgba(255, 0, 0, 0.75), -0.05em -0.025em 0 rgba(0, 255, 0, 0.75), 0.025em 0.05em 0 rgba(0, 0, 255, 0.75); }
  14% { text-shadow: 0.05em 0 0 rgba(255, 0, 0, 0.75), -0.05em -0.025em 0 rgba(0, 255, 0, 0.75), 0.025em 0.05em 0 rgba(0, 0, 255, 0.75); }
  15% { text-shadow: -0.05em -0.025em 0 rgba(255, 0, 0, 0.75), 0.025em 0.025em 0 rgba(0, 255, 0, 0.75), -0.05em -0.05em 0 rgba(0, 0, 255, 0.75); }
  49% { text-shadow: -0.05em -0.025em 0 rgba(255, 0, 0, 0.75), 0.025em 0.025em 0 rgba(0, 255, 0, 0.75), -0.05em -0.05em 0 rgba(0, 0, 255, 0.75); }
  50% { text-shadow: 0.025em 0.05em 0 rgba(255, 0, 0, 0.75), 0.05em 0 0 rgba(0, 255, 0, 0.75), 0 -0.05em 0 rgba(0, 0, 255, 0.75); }
  99% { text-shadow: 0.025em 0.05em 0 rgba(255, 0, 0, 0.75), 0.05em 0 0 rgba(0, 255, 0, 0.75), 0 -0.05em 0 rgba(0, 0, 255, 0.75); }
  100% { text-shadow: -0.025em 0 0 rgba(255, 0, 0, 0.75), -0.025em -0.025em 0 rgba(0, 255, 0, 0.75), -0.025em -0.05em 0 rgba(0, 0, 255, 0.75); }
}
</style> 