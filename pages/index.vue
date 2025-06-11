<template>
  <div class="min-h-screen bg-gray-900 text-white p-4 flex flex-col items-center justify-center">
    <div class="w-full max-w-4xl">
      <div class="text-center mb-10">
        <h1 class="text-3xl md:text-4xl font-bold mb-2">工具箱</h1>
        <p class="text-gray-400">精选实用工具，让你的工作更高效</p>
      </div>
      
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        <NuxtLink 
          :to="tools[0].path" 
          class="col-span-1 md:col-span-2 lg:col-span-2 self-center"
        >
          <a-card 
            hoverable 
            class="bg-gray-800 border-gray-700 shadow-lg transition-all duration-300 hover:shadow-xl hover:bg-gray-750"
          >
            <template #title>
              <div class="flex items-center">
                <div class="bg-blue-600 p-2 rounded-lg mr-3">
                  <i class="fa fa-cloud text-white text-xl"></i>
                </div>
                <h2 class="text-2xl font-bold text-white">阿里云盘TV授权</h2>
              </div>
            </template>
            <div class="flex flex-col md:flex-row items-center">
              <div class="md:w-1/3 mb-4 md:mb-0 md:pr-4">
                <img 
                  src="https://picsum.photos/seed/alipan/300/200" 
                  alt="阿里云盘TV授权" 
                  class="w-full h-auto rounded-lg shadow-md"
                >
              </div>
              <div class="md:w-2/3">
                <p class="text-gray-300 text-lg mb-4">
                  获取阿里云盘TV端的授权令牌，轻松在电视上访问您的阿里云盘资源
                </p>
                <div class="flex justify-between items-center">
                  <span class="text-blue-400 text-sm font-medium">
                    <i class="fa fa-info-circle mr-1"></i> 简单三步完成授权
                  </span>
                  <button class="bg-blue-600 hover:bg-blue-700 text-white px-4 py-2 rounded-lg transition-all duration-300 transform hover:scale-105">
                    立即授权
                  </button>
                </div>
              </div>
            </div>
          </a-card>
        </NuxtLink>

<script setup>
const tools = [
 {
    id: 1,
    title: '阿里云盘TV授权',
    description: '获取阿里云盘TV端的授权令牌',
    path: '/alipan-tv-token',
    available: true
  },
  // 可以添加更多工具
];
</script>

<style scoped>
/* 全局样式 */
body {
  background-color: #121212;
}

/* 卡片悬停效果增强 */
.a-card {
  border-radius: 12px;
  overflow: hidden;
}

.a-card:hover {
  transform: translateY(-5px);
}

/* 按钮样式 */
button {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
}

button i {
  font-size: 14px;
}
</style>
