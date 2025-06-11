<template>
  <div class="min-h-screen bg-gradient-to-b from-gray-50 to-gray-100 dark:from-gray-900 dark:to-gray-800 flex flex-col">
    <!-- 顶部导航 -->
    <header class="bg-white/80 dark:bg-gray-900/80 backdrop-blur-md shadow-sm sticky top-0 z-10 transition-all duration-300">
      <div class="container mx-auto px-4 py-3 flex items-center justify-between">
        <div class="flex items-center space-x-2">
          <div class="w-8 h-8 rounded-lg bg-blue-500 flex items-center justify-center text-white">
            <i class="fa fa-tools"></i>
          </div>
          <h1 class="text-lg sm:text-xl font-bold text-gray-800 dark:text-white">工具箱</h1>
        </div>
        <div class="flex items-center space-x-4">
          <button class="text-gray-600 dark:text-gray-300 hover:text-gray-900 dark:hover:text-white transition-colors">
            <i class="fa fa-search"></i>
          </button>
          <button class="text-gray-600 dark:text-gray-300 hover:text-gray-900 dark:hover:text-white transition-colors">
            <i class="fa fa-user"></i>
          </button>
          <button class="text-gray-600 dark:text-gray-300 hover:text-gray-900 dark:hover:text-white transition-colors" @click="toggleDarkMode">
            <i class="fa fa-moon-o dark:hidden"></i>
            <i class="fa fa-sun-o hidden dark:inline-block"></i>
          </button>
        </div>
      </div>
    </header>

    <!-- 主内容区 -->
    <main class="flex-grow container mx-auto px-4 py-8">
      <div class="max-w-3xl mx-auto">
        <div class="text-center mb-12">
          <h2 class="text-3xl sm:text-4xl font-bold text-gray-800 dark:text-white mb-4">阿里云盘TV授权</h2>
          <p class="text-lg text-gray-600 dark:text-gray-300 max-w-2xl mx-auto">
            一键获取阿里云盘TV端的授权令牌，轻松在电视上访问你的云盘内容
          </p>
        </div>
        
        <div class="bg-white dark:bg-gray-800 rounded-2xl shadow-xl overflow-hidden transition-all duration-300 hover:shadow-2xl">
          <div class="p-6 sm:p-8">
            <div class="flex flex-col sm:flex-row items-center mb-6">
              <div class="w-16 h-16 sm:w-20 sm:h-20 rounded-2xl bg-blue-100 dark:bg-blue-900/30 flex items-center justify-center text-blue-600 dark:text-blue-400 mb-4 sm:mb-0 sm:mr-6">
                <i class="fa fa-cloud text-3xl"></i>
              </div>
              <div>
                <h3 class="text-xl sm:text-2xl font-semibold text-gray-800 dark:text-white mb-2">获取授权令牌</h3>
                <p class="text-gray-600 dark:text-gray-300">安全、便捷地获取阿里云盘TV端的访问权限</p>
              </div>
            </div>
            
            <div class="space-y-6">
              <div class="bg-gray-50 dark:bg-gray-700/50 rounded-xl p-5">
                <div class="flex items-start mb-4">
                  <div class="w-8 h-8 rounded-full bg-blue-100 dark:bg-blue-900/30 flex items-center justify-center text-blue-600 dark:text-blue-400 mr-3 flex-shrink-0">
                    <i class="fa fa-info"></i>
                  </div>
                  <p class="text-gray-600 dark:text-gray-300">
                    使用此工具获取的授权令牌有效期为14天，请妥善保管。授权过程不会获取您的账号密码，仅生成访问令牌。
                  </p>
                </div>
                
                <div class="flex flex-col sm:flex-row gap-4">
                  <button 
                    class="flex-1 bg-blue-500 hover:bg-blue-600 text-white font-medium py-3 px-4 rounded-lg transition-colors flex items-center justify-center btn-hover"
                    @click="navigateToTokenPage"
                  >
                    <i class="fa fa-key mr-2"></i> 获取授权令牌
                  </button>
                  <button class="flex-1 bg-gray-200 dark:bg-gray-700 hover:bg-gray-300 dark:hover:bg-gray-600 text-gray-700 dark:text-gray-200 font-medium py-3 px-4 rounded-lg transition-colors flex items-center justify-center">
                    <i class="fa fa-question-circle mr-2"></i> 帮助说明
                  </button>
                </div>
              </div>
              
              <div class="border-t border-gray-100 dark:border-gray-700 pt-6">
                <h4 class="text-lg font-medium text-gray-800 dark:text-white mb-4">授权步骤</h4>
                <div class="space-y-4">
                  <div class="flex">
                    <div class="w-8 h-8 rounded-full bg-blue-100 dark:bg-blue-900/30 flex items-center justify-center text-blue-600 dark:text-blue-400 mr-3 flex-shrink-0">
                      <span class="font-medium">1</span>
                    </div>
                    <p class="text-gray-600 dark:text-gray-300">点击上方"获取授权令牌"按钮</p>
                  </div>
                  <div class="flex">
                    <div class="w-8 h-8 rounded-full bg-blue-100 dark:bg-blue-900/30 flex items-center justify-center text-blue-600 dark:text-blue-400 mr-3 flex-shrink-0">
                      <span class="font-medium">2</span>
                    </div>
                    <p class="text-gray-600 dark:text-gray-300">使用阿里云盘手机APP扫描弹出的二维码</p>
                  </div>
                  <div class="flex">
                    <div class="w-8 h-8 rounded-full bg-blue-100 dark:bg-blue-900/30 flex items-center justify-center text-blue-600 dark:text-blue-400 mr-3 flex-shrink-0">
                      <span class="font-medium">3</span>
                    </div>
                    <p class="text-gray-600 dark:text-gray-300">在手机上确认授权请求</p>
                  </div>
                  <div class="flex">
                    <div class="w-8 h-8 rounded-full bg-blue-100 dark:bg-blue-900/30 flex items-center justify-center text-blue-600 dark:text-blue-400 mr-3 flex-shrink-0">
                      <span class="font-medium">4</span>
                    </div>
                    <p class="text-gray-600 dark:text-gray-300">复制生成的授权令牌到TV端应用</p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        
        <div class="mt-12 text-center">
          <p class="text-gray-500 dark:text-gray-400">
            其他工具正在开发中，敬请期待
          </p>
        </div>
      </div>
    </main>

    <!-- 页脚 -->
    <footer class="bg-white dark:bg-gray-900 py-6 border-t border-gray-200 dark:border-gray-800">
      <div class="container mx-auto px-4">
        <div class="flex flex-col md:flex-row justify-between items-center">
          <div class="mb-4 md:mb-0">
            <div class="flex items-center space-x-2">
              <div class="w-6 h-6 rounded-lg bg-blue-500 flex items-center justify-center text-white">
                <i class="fa fa-tools text-xs"></i>
              </div>
              <span class="text-sm font-medium text-gray-700 dark:text-gray-300">工具箱</span>
            </div>
          </div>
          <div class="flex space-x-6">
            <a href="#" class="text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-300 transition-colors text-sm">
              隐私政策
            </a>
            <a href="#" class="text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-300 transition-colors text-sm">
              使用条款
            </a>
            <a href="#" class="text-gray-500 dark:text-gray-400 hover:text-gray-700 dark:hover:text-gray-300 transition-colors text-sm">
              联系我们
            </a>
          </div>
        </div>
        <div class="mt-4 text-center text-gray-500 dark:text-gray-400 text-xs">
          &copy; {{ new Date().getFullYear() }} 工具箱. 保留所有权利.
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import { useRouter } from 'vue-router'; // 引入路由钩子

// 深色模式状态
const isDarkMode = ref(false);
const router = useRouter(); // 获取路由实例

// 导航到令牌页面
const navigateToTokenPage = () => {
  router.push(tools[0].path);
};

// 切换深色模式
const toggleDarkMode = () => {
  isDarkMode.value = !isDarkMode.value;
  document.documentElement.classList.toggle('dark', isDarkMode.value);
  localStorage.setItem('darkMode', isDarkMode.value ? 'true' : 'false');
};

// 初始化深色模式
onMounted(() => {
  const savedMode = localStorage.getItem('darkMode');
  if (savedMode === 'true' || (!savedMode && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
    isDarkMode.value = true;
    document.documentElement.classList.add('dark');
  }
});

// 工具数据
const tools = ref([
  {
    id: 1,
    title: '阿里云盘TV授权',
    description: '获取阿里云盘TV端的授权令牌，方便在电视上使用',
    path: '/alipan-tv-token',
    available: true,
    icon: 'fa fa-cloud',
    updated: '2023-05-15'
  }
]);
</script>

<style scoped>
/* 导入Tailwind CSS和Font Awesome */
@tailwind base;
@tailwind components;
@tailwind utilities;

/* 导入Font Awesome */
@import url('https://cdn.jsdelivr.net/npm/font-awesome@4.7.0/css/font-awesome.min.css');

/* 自定义滚动条 */
::-webkit-scrollbar {
  width: 8px;
  height: 8px;
}

::-webkit-scrollbar-track {
  background: #f1f1f1;
  border-radius: 4px;
}

::-webkit-scrollbar-thumb {
  background: #c1c1c1;
  border-radius: 4px;
}

::-webkit-scrollbar-thumb:hover {
  background: #a1a1a1;
}

/* 深色模式滚动条 */
.dark ::-webkit-scrollbar-track {
  background: #2d2d2d;
}

.dark ::-webkit-scrollbar-thumb {
  background: #4d4d4d;
}

.dark ::-webkit-scrollbar-thumb:hover {
  background: #6d6d6d;
}

/* 自定义动画 */
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(10px); }
  to { opacity: 1; transform: translateY(0); }
}

.fade-in {
  animation: fadeIn 0.5s ease forwards;
}

/* 按钮悬停效果 */
.btn-hover {
  transition: all 0.3s ease;
}

.btn-hover:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}
</style>
