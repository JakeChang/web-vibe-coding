<template>
  <div class="min-h-screen bg-gray-100 pb-12">
    <!-- iOS 風格頁面 -->
    <div class="fixed top-0 left-0 right-0 bg-gray-200 z-10">
      <div class="max-w-3xl mx-auto px-4 py-3 flex items-center">
        <h1 class="text-center text-lg font-semibold text-black flex-grow">SwiftUI 訂閱追蹤器</h1>
      </div>
    </div>

    <div class="max-w-3xl mx-auto pt-20 px-4">
      <!-- 標題區塊 -->
      <div class="rounded-xl bg-white shadow-sm mb-6">
        <div class="p-4">
          <h1 class="text-2xl font-bold text-black">Vibe Coding 005</h1>
          <p class="text-gray-500 mt-1">製作一個訂閱追蹤器，使用 SwiftUI 開發 iOS App</p>
        </div>
      </div>

      <!-- 新增資料規格區塊 -->
      <div class="rounded-xl bg-white shadow-sm mb-6">
        <div class="px-4 py-3 border-b border-gray-200">
          <h2 class="text-lg font-semibold">新增資料規格</h2>
        </div>
        <div class="p-4">
          <div class="rounded-lg bg-gray-50 p-4 mb-4">
            <h3 class="font-medium text-gray-900 mb-2">頁面規格</h3>
            <p class="text-gray-700 mb-4">SwiftUI 專案</p>

            <h3 class="font-medium text-gray-900 mb-2">頁面結構</h3>
            <p class="text-gray-700 mb-4">新增或者修改訂閱的頁面</p>

            <h3 class="font-medium text-gray-900 mb-2">欄位</h3>
            <ul class="list-disc pl-5 text-gray-700 mb-4">
              <li>訂閱平台（String，必填）</li>
              <li>金額（Decimal，必填，> 0）</li>
              <li>支付週期（Enum: 月付/年付，必填）</li>
              <li>開始日期（Date，必填）</li>
              <li>下次付款日（Date，系統自動推算，可修改，非必填，需根據目前日期推算下次付款日）</li>
            </ul>

            <h3 class="font-medium text-gray-900 mb-2">功能要求</h3>
            <ul class="list-disc pl-5 text-gray-700 mb-4">
              <li>表單驗證：訂閱平台、金額、支付週期、開始日期為必填</li>
              <li>金額需為有效數值（> 0）</li>
              <li>下次付款日自動根據週期與開始日推算，可手動修改</li>
              <li>儲存時顯示 loading、錯誤訊息提示
                <ul class="list-disc pl-5">
                  <li>若驗證失敗，顯示對應錯誤提示文字於欄位下方</li>
                </ul>
              </li>
              <li>儲存成功後自動跳轉到訂閱列表</li>
              <li>資料儲存在本地資料庫，使用 SwiftData 資料庫</li>
              <li>新增與修改資料共用此頁</li>
            </ul>

            <h3 class="font-medium text-gray-900 mb-2">實現檔案（使用 MVVM 架構）</h3>
            <p class="text-gray-700 mb-2">需要新增以下檔案：</p>
            <ol class="list-decimal pl-5 text-gray-700 mb-4">
              <li><strong>AddView.swift</strong>
                <ul class="list-disc pl-5">
                  <li>SwiftUI 表單 UI</li>
                </ul>
              </li>
              <li><strong>AddViewModel.swift</strong>
                <ul class="list-disc pl-5">
                  <li>處理表單驗證邏輯</li>
                  <li>提供表單提交方法</li>
                  <li>處理錯誤訊息</li>
                  <li>管理 UI 狀態</li>
                </ul>
              </li>
              <li><strong>AddModel.swift</strong>
                <ul class="list-disc pl-5">
                  <li>定義資料模型結構</li>
                </ul>
              </li>
            </ol>

            <p class="text-gray-700 mb-2">這三個檔案都產生在 TestDemo/Add/ 下即可，不需要再切子目錄。</p>
            <pre class="bg-gray-100 p-2 rounded text-gray-800 text-sm mb-4">TestDemo/
└── Add/
    ├── AddView.swift
    ├── AddViewModel.swift
    └── AddModel.swift</pre>
          </div>
        </div>
      </div>

      <!-- 列表資料規格區塊 -->
      <div class="rounded-xl bg-white shadow-sm mb-6">
        <div class="px-4 py-3 border-b border-gray-200">
          <h2 class="text-lg font-semibold">列表資料規格</h2>
        </div>
        <div class="p-4">
          <div class="rounded-lg bg-gray-50 p-4 mb-4">
            <h3 class="font-medium text-gray-900 mb-2">頁面規格</h3>

            <h3 class="font-medium text-gray-900 mb-2">頁面結構</h3>
            <p class="text-gray-700 mb-4">訂閱列表</p>

            <h3 class="font-medium text-gray-900 mb-2">欄位</h3>
            <ul class="list-disc pl-5 text-gray-700 mb-4">
              <li>訂閱平台</li>
              <li>金額</li>
              <li>支付週期</li>
              <li>開始日期</li>
              <li>下次付款日</li>
            </ul>

            <h3 class="font-medium text-gray-900 mb-2">功能要求</h3>
            <ul class="list-disc pl-5 text-gray-700 mb-4">
              <li>右上角有一個新增按鈕，可以跳轉到 AddView.swift 頁面</li>
              <li>讀取本地資料庫來顯示列表，使用 SwiftData</li>
              <li>無資料時，要顯示沒有任何訂閱資料</li>
              <li>列表頁面可以點選，點選會會進入到 AddView.swift 可以修改資料</li>
            </ul>

            <h3 class="font-medium text-gray-900 mb-2">實現檔案（使用 MVVM 架構）</h3>
            <p class="text-gray-700 mb-2">需要新增以下檔案：</p>
            <ol class="list-decimal pl-5 text-gray-700 mb-4">
              <li><strong>ContentView.swift</strong>
                <ul class="list-disc pl-5">
                  <li>SwiftUI 列表 UI</li>
                </ul>
              </li>
              <li><strong>ContentViewModel.swift</strong>
                <ul class="list-disc pl-5">
                  <li>管理 UI 狀態</li>
                </ul>
              </li>
              <li><strong>ContentModel.swift</strong>
                <ul class="list-disc pl-5">
                  <li>定義資料模型結構</li>
                </ul>
              </li>
            </ol>

            <p class="text-gray-700 mb-2">這三個檔案都產生在 TestDemo/List/ 下即可，不需要再切子目錄。</p>
            <pre class="bg-gray-100 p-2 rounded text-gray-800 text-sm mb-4">TestDemo/
└── List/
    ├── ContentView.swift
    ├── ContentViewModel.swift
    └── ContentModel.swift</pre>

            <h3 class="font-medium text-gray-900 mb-2">備註</h3>
            <p class="text-gray-700 mb-2">需要在主程式 TestDemoApp.swift 引用相關 SwiftData 的 Model</p>
          </div>
        </div>
      </div>

      <!-- 結果區塊 -->
      <div class="rounded-xl bg-white shadow-sm mb-6">
        <div class="px-4 py-3 border-b border-gray-200">
          <h2 class="text-lg font-semibold">結果</h2>
        </div>
        <div class="p-4">
          <ul class="space-y-3">
            <li class="flex items-center">
              <span class="text-gray-700 mr-2">程式碼:</span>
              <a href="https://xxx" class="text-blue-500 hover:underline">https://xxx</a>
            </li>
            <li class="flex items-center">
              <span class="text-gray-700 mr-2">線上 Demo:</span>
              <a href="https://xxx" class="text-blue-500 hover:underline">https://xxx</a>
            </li>
            <li class="flex items-center">
              <span class="text-gray-700 mr-2">youtube 講解:</span>
              <a href="https://xxx" class="text-blue-500 hover:underline">https://xxx</a>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
// 不需要額外的腳本邏輯
</script>

<style>
/* iOS 風格自定義樣式 */
body {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style> 