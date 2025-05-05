<template>
  <div class="min-h-screen bg-gray-100 py-12 px-4 sm:px-6 lg:px-8">
    <div class="max-w-4xl mx-auto">
      <div class="text-center mb-12">
        <h1 class="text-4xl font-bold text-gray-900 mb-4">傑克 IT 誌 - Vibe Coding</h1>
        <p class="text-xl text-gray-600">歡迎來到氛圍開發技術指南</p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
        <!-- 001 卡片 -->
        <div class="bg-black rounded-lg shadow-lg overflow-hidden transform transition duration-300 hover:scale-105 hover:shadow-xl">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-green-500 mr-2 font-mono">[系統]</span>
              <span class="text-green-400 font-mono">連接成功...</span>
            </div>
            <h2 class="text-2xl font-bold text-green-500 mb-4 font-mono">Vibe Coding 001</h2>
            <p class="text-green-400 mb-6 font-mono">使用 Vue + Nuxt 製作酷炫 blog</p>
            <div class="mt-6">
              <NuxtLink to="/001" class="inline-block bg-green-500 hover:bg-green-600 text-black font-bold py-2 px-4 rounded border border-green-700 transition duration-300">
                <span class="font-mono">[訪問頁面]</span>
              </NuxtLink>
            </div>
          </div>
        </div>
        
        <!-- 002 卡片 -->
        <div class="bg-white rounded-lg shadow-lg overflow-hidden transform transition duration-300 hover:scale-105 hover:shadow-xl">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-blue-600 font-medium">Google</span>
              <span class="text-red-500 font-medium ml-1">試算表</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-800 mb-4">Vibe Coding 002</h2>
            <p class="text-gray-600 mb-6">使用 Google 試算表製作 API</p>
            <div class="mt-6">
              <NuxtLink to="/002" class="inline-block bg-blue-600 hover:bg-blue-700 text-white font-medium py-2 px-4 rounded transition duration-300">
                訪問頁面
              </NuxtLink>
            </div>
          </div>
        </div>
        
        <!-- 003 卡片 -->
        <div class="bg-amber-50 rounded-lg shadow-lg overflow-hidden transform transition duration-300 hover:scale-105 hover:shadow-xl">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-amber-800 font-medium">傑克 IT 誌</span>
              <span class="text-red-600 font-medium ml-1">Vibe Coding</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-800 mb-4">Vibe Coding 003</h2>
            <p class="text-gray-600 mb-6">Nuxt.js 串接 Google Sheet API</p>
            <div class="mt-6">
              <NuxtLink to="/003" class="inline-block bg-red-100 hover:bg-red-200 text-red-800 font-medium py-2 px-4 rounded border border-amber-200 transition duration-300">
                訪問頁面
              </NuxtLink>
            </div>
          </div>
        </div>
      </div>

      <div class="mt-12 text-center">
        <p class="text-gray-600">
            傑克 IT 誌 - Vibe Coding
        </p>
      </div>
    </div>
  </div>
</template>

<style scoped>
@keyframes pulse {
  0% { opacity: 1; }
  50% { opacity: 0.5; }
  100% { opacity: 1; }
}

.text-green-400 {
  animation: pulse 2s infinite;
}
</style>