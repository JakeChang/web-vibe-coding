<template>
  <div class="min-h-screen bg-gray-100 py-12 px-4 sm:px-6 lg:px-8">
    <div class="max-w-4xl mx-auto">
      <div class="text-center mb-12">
        <h1 class="text-4xl font-bold text-gray-900 mb-4">傑克 IT 誌 - Vibe Coding</h1>
        <p class="text-xl text-gray-600">歡迎來到氛圍開發技術指南</p>
        
        <!-- 進度區塊 -->
        <div class="mt-6 max-w-md mx-auto">
          <div class="flex justify-between items-center mb-2">
            <span class="text-gray-700 font-medium">進度</span>
            <span class="text-gray-700 font-medium">5天/30天 (16.67%)</span>
          </div>
          <div class="w-full bg-gray-200 rounded-full h-2.5">
            <div class="bg-blue-600 h-2.5 rounded-full" style="width: 16.67%"></div>
          </div>
        </div>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
        <!-- 001 卡片 -->
        <div class="bg-black rounded-lg shadow-lg overflow-hidden transform transition duration-300 hover:scale-105 hover:shadow-xl">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-green-500 mr-2 font-mono">[分類]</span>
              <span class="text-green-400 font-mono">Web</span>
            </div>
            <h2 class="text-2xl font-bold text-green-500 mb-4 font-mono">Vibe Coding 001</h2>
            <p class="text-green-400 mb-6 font-mono">使用 Vue + Nuxt 製作酷炫 blog</p>
            <div class="mt-6">
              <NuxtLink to="/001" class="inline-block bg-green-500 hover:bg-green-600 text-black font-bold py-2 px-4 rounded border border-green-700 transition duration-300">
                <span class="font-mono">訪問頁面</span>
              </NuxtLink>
            </div>
          </div>
        </div>
        
        <!-- 002 卡片 -->
        <div class="bg-white rounded-lg shadow-lg overflow-hidden transform transition duration-300 hover:scale-105 hover:shadow-xl">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-blue-600 font-medium">[分類]</span>
              <span class="text-red-500 font-medium ml-1">API</span>
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
              <span class="text-amber-800 font-medium">[分類]</span>
              <span class="text-red-600 font-medium ml-1">Web</span>
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
        
        <!-- 004 卡片 -->
        <div class="bg-amber-50 rounded-lg shadow-lg overflow-hidden transform transition duration-300 hover:scale-105 hover:shadow-xl">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-amber-700 font-medium">[分類]</span>
              <span class="text-blue-600 font-medium ml-1">Web</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-800 mb-4">Vibe Coding 004</h2>
            <p class="text-gray-600 mb-6">購買物品紀錄系統設計規格</p>
            <div class="mt-6">
              <NuxtLink to="/004" class="inline-block bg-amber-100 hover:bg-amber-200 text-amber-800 font-medium py-2 px-4 rounded border border-amber-300 transition duration-300">
                訪問頁面
              </NuxtLink>
            </div>
          </div>
        </div>
        
        <!-- 005 卡片 -->
        <div class="bg-gray-50 rounded-lg shadow-lg overflow-hidden transform transition duration-300 hover:scale-105 hover:shadow-xl">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-600 font-medium">[分類]</span>
              <span class="text-blue-500 font-medium ml-1">iOS</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-800 mb-4">Vibe Coding 005</h2>
            <p class="text-gray-600 mb-6">SwiftUI 訂閱追蹤器開發規格</p>
            <div class="mt-6">
              <NuxtLink to="/005" class="inline-block bg-blue-100 hover:bg-blue-200 text-blue-800 font-medium py-2 px-4 rounded border border-blue-200 transition duration-300">
                訪問頁面
              </NuxtLink>
            </div>
          </div>
        </div>
        
        <!-- 006 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 006</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
        
        <!-- 007 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 007</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
        
        <!-- 008 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 008</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
        
        <!-- 009 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 009</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
        
        <!-- 010 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 010</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
        
        <!-- 011 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 011</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
        
        <!-- 012 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 012</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
        
        <!-- 013 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 013</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
        
        <!-- 014 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 014</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
        
        <!-- 015 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 015</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
        
        <!-- 016 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 016</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
        
        <!-- 017 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 017</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
        
        <!-- 018 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 018</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
        
        <!-- 019 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 019</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
        
        <!-- 020 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 020</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
        
        <!-- 021 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 021</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
        
        <!-- 022 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 022</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
        
        <!-- 023 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 023</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
        
        <!-- 024 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 024</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
        
        <!-- 025 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 025</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
        
        <!-- 026 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 026</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
        
        <!-- 027 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 027</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
        
        <!-- 028 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 028</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
        
        <!-- 029 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 029</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
        
        <!-- 030 卡片 (未完成) -->
        <div class="bg-gray-200 rounded-lg shadow-sm overflow-hidden transform transition duration-300 hover:scale-105 opacity-70">
          <div class="px-6 py-8">
            <div class="flex items-center mb-4">
              <span class="text-gray-500 font-medium">[未完成]</span>
            </div>
            <h2 class="text-2xl font-medium text-gray-500 mb-4">Vibe Coding 030</h2>
            <p class="text-gray-500 mb-6">即將推出...</p>
            <div class="mt-6">
              <button disabled class="inline-block bg-gray-300 text-gray-500 font-medium py-2 px-4 rounded border border-gray-400 cursor-not-allowed">
                敬請期待
              </button>
            </div>
          </div>
        </div>
      </div>

      <div class="mt-12 text-center">
        <p class="text-gray-600">
            傑克 IT 誌 - Vibe Coding
        </p>
        <a href="https://jkone.dev/" rel="noopener noreferrer" class="inline-block mt-2 text-blue-600 hover:text-blue-800 hover:underline transition duration-300">
          JK__
        </a>
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