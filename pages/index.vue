<template>
  <div class="min-h-screen bg-gray-50 flex flex-col">
    <!-- 顶部导航 -->
    <header class="bg-white shadow-sm sticky top-0 z-10">
      <div class="container mx-auto px-4 py-4 flex items-center justify-between">
        <h1 class="text-xl sm:text-2xl font-bold text-gray-800">工具箱</h1>
        <div class="flex items-center space-x-4">
          <button class="text-gray-600 hover:text-gray-900 transition-colors">
            <i class="fa fa-search"></i>
          </button>
          <button class="text-gray-600 hover:text-gray-900 transition-colors">
            <i class="fa fa-user"></i>
          </button>
        </div>
      </div>
    </header>

    <!-- 主内容区 -->
    <main class="flex-grow container mx-auto px-4 py-6 sm:py-8">
      <div class="max-w-4xl mx-auto">
        <h2 class="text-xl sm:text-2xl font-semibold text-gray-800 mb-4 sm:mb-6">常用工具</h2>
        
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4 sm:gap-6">
          <template v-for="tool in tools" :key="tool.id">
            <div 
              class="bg-white rounded-xl shadow-md overflow-hidden transition-all duration-300 hover:shadow-lg hover:-translate-y-1 cursor-pointer"
              :class="tool.available ? '' : 'opacity-50 cursor-not-allowed'"
            >
              <div class="p-4 sm:p-6">
                <div class="flex items-center mb-3 sm:mb-4">
                  <div class="w-10 sm:w-12 h-10 sm:h-12 rounded-lg bg-blue-100 flex items-center justify-center text-blue-600">
                    <i :class="tool.icon" class="text-lg sm:text-xl"></i>
                  </div>
                  <h3 class="ml-3 sm:ml-4 text-lg sm:text-xl font-medium text-gray-800">{{ tool.title }}</h3>
                </div>
                <p class="text-gray-600 mb-3 sm:mb-4 text-sm sm:text-base">{{ tool.description }}</p>
                <div class="flex justify-between items-center">
                  <span class="text-xs sm:text-sm text-gray-500">更新于 {{ tool.updated }}</span>
                  <NuxtLink 
                    :to="tool.path"
                    class="text-blue-600 hover:text-blue-800 font-medium transition-colors text-sm sm:text-base"
                    :class="tool.available ? '' : 'pointer-events-none'"
                  >
                    前往使用 <i class="fa fa-arrow-right ml-1"></i>
                  </NuxtLink>
                </div>
              </div>
            </div>
          </template>
        </div>
      </div>
    </main>

    <!-- 页脚 -->
    <footer class="bg-gray-800 text-white py-6 sm:py-8">
      <div class="container mx-auto px-4">
        <div class="flex flex-col sm:flex-row justify-between items-center">
          <div class="mb-4 sm:mb-0">
            <h3 class="text-lg sm:text-xl font-bold mb-2">工具箱</h3>
            <p class="text-gray-400 text-sm">便捷工具集合，提升工作效率</p>
          </div>
          <div class="flex space-x-4 sm:space-x-6">
            <a href="#" class="text-gray-400 hover:text-white transition-colors">
              <i class="fa fa-github text-lg sm:text-xl"></i>
            </a>
            <a href="#" class="text-gray-400 hover:text-white transition-colors">
              <i class="fa fa-twitter text-lg sm:text-xl"></i>
            </a>
            <a href="#" class="text-gray-400 hover:text-white transition-colors">
              <i class="fa fa-linkedin text-lg sm:text-xl"></i>
            </a>
          </div>
        </div>
        <div class="border-t border-gray-700 mt-4 sm:mt-6 pt-4 sm:pt-6 text-center text-gray-400 text-xs sm:text-sm">
          &copy; {{ new Date().getFullYear() }} 工具箱. 保留所有权利.
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref } from 'vue';

// 工具列表数据
const tools = ref([
  {
    id: 1,
    title: '阿里云盘TV授权',
    description: '获取阿里云盘TV端的授权令牌，方便在电视上使用',
    path: '/alipan-tv-token',
    available: true,
    icon: 'fa fa-cloud',
    updated: '2023-05-15'
  },
  {
    id: 2,
    title: '图片压缩工具',
    description: '无损压缩图片文件，减小文件体积',
    path: '/image-compressor',
    available: true,
    icon: 'fa fa-image',
    updated: '2023-05-10'
  },
  {
    id: 3,
    title: 'PDF转Word',
    description: '将PDF文档转换为可编辑的Word文档',
    path: '/pdf-to-word',
    available: false,
    icon: 'fa fa-file-pdf-o',
    updated: '2023-05-05'
  },
  {
    id: 4,
    title: '二维码生成器',
    description: '将文本、链接等内容转换为二维码',
    path: '/qrcode-generator',
    available: true,
    icon: 'fa fa-qrcode',
    updated: '2023-04-28'
  }
]);

// 对工具列表进行排序
tools.value.sort((a, b) => a.id - b.id);
</script>

<style scoped>
/* 导入Font Awesome */
@import url('https://cdn.jsdelivr.net/npm/font-awesome@4.7.0/css/font-awesome.min.css');

/* 自定义样式 */
a-card {
  display: block;
  border: 1px solid #e5e7eb;
  border-radius: 0.5rem;
  padding: 1.5rem;
  transition: all 0.3s ease;
}

a-card:hover {
  box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
  transform: translateY(-2px);
}
</style>
