<template>
  <div class="min-h-screen bg-gradient-to-br from-gray-900 via-gray-800 to-gray-900 text-white flex flex-col">
    <!-- 导航栏 -->
    <header class="w-full py-4 px-6 md:px-10 bg-gray-900/80 backdrop-blur-md border-b border-gray-800">
      <div class="max-w-7xl mx-auto flex justify-between items-center">
        <div class="flex items-center space-x-2">
          <div class="w-10 h-10 rounded-lg bg-blue-600 flex items-center justify-center">
            <i class="fa fa-cube text-white text-xl"></i>
          </div>
          <h1 class="text-xl md:text-2xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-blue-400 to-purple-500">
            ToolKit
          </h1>
        </div>
        <nav class="hidden md:flex space-x-8">
          <a href="#" class="text-gray-300 hover:text-white transition-colors duration-200">首页</a>
          <a href="#" class="text-gray-300 hover:text-white transition-colors duration-200">工具</a>
          <a href="#" class="text-gray-300 hover:text-white transition-colors duration-200">文档</a>
          <a href="#" class="text-gray-300 hover:text-white transition-colors duration-200">关于</a>
        </nav>
        <button class="md:hidden text-gray-300 hover:text-white">
          <i class="fa fa-bars text-xl"></i>
        </button>
      </div>
    </header>

    <!-- 主要内容区 -->
    <main class="flex-grow flex flex-col items-center justify-center px-4 py-12 md:py-20">
      <div class="w-full max-w-4xl">
        <div class="text-center mb-12 md:mb-16">
          <h1 class="text-3xl md:text-5xl font-bold mb-4 bg-clip-text text-transparent bg-gradient-to-r from-blue-400 to-purple-500">
            阿里云盘TV授权
          </h1>
          <p class="text-xl text-gray-300 max-w-2xl mx-auto">
            轻松获取阿里云盘TV端的授权令牌，在大屏设备上畅享云盘资源
          </p>
        </div>
        
        <!-- 主卡片 -->
        <div class="flex justify-center">
          <NuxtLink 
            :to="tools[0].path" 
            class="w-full max-w-3xl"
          >
            <a-card 
              hoverable 
              class="bg-gray-800/60 backdrop-blur-sm border border-gray-700/50 rounded-2xl shadow-2xl shadow-blue-900/10 overflow-hidden transition-all duration-500 hover:shadow-blue-500/10 hover:scale-[1.01] hover:bg-gray-800/80"
            >
              <div class="p-6 md:p-8">
                <template #title>
                  <div class="flex items-center mb-6">
                    <div class="w-12 h-12 rounded-xl bg-blue-600 flex items-center justify-center mr-4">
                      <i class="fa fa-cloud text-white text-2xl"></i>
                    </div>
                    <h2 class="text-2xl md:text-3xl font-bold text-white">阿里云盘TV授权</h2>
                  </div>
                </template>
                
                <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-center">
                  <div class="relative">
                    <div class="absolute -top-4 -right-4 w-24 h-24 bg-blue-500/20 rounded-full blur-2xl"></div>
                    <img 
                      src="https://picsum.photos/seed/alipan/600/400" 
                      alt="阿里云盘TV授权" 
                      class="w-full h-auto rounded-xl shadow-xl transform hover:scale-[1.02] transition-transform duration-500"
                    >
                    <div class="absolute -bottom-3 -left-3 w-20 h-20 bg-purple-500/20 rounded-full blur-2xl"></div>
                  </div>
                  
                  <div class="space-y-6">
                    <p class="text-lg text-gray-200 leading-relaxed">
                      通过简单的三步授权流程，您可以获取阿里云盘TV端的访问令牌，在智能电视、机顶盒等大屏设备上轻松访问您的云盘资源。
                    </p>
                    
                    <div class="space-y-4">
                      <div class="flex items-start space-x-3">
                        <div class="w-6 h-6 rounded-full bg-blue-500 flex items-center justify-center mt-0.5 flex-shrink-0">
                          <i class="fa fa-check text-xs"></i>
                        </div>
                        <p class="text-gray-300">使用阿里云账号登录授权页面</p>
                      </div>
                      <div class="flex items-start space-x-3">
                        <div class="w-6 h-6 rounded-full bg-blue-500 flex items-center justify-center mt-0.5 flex-shrink-0">
                          <i class="fa fa-check text-xs"></i>
                        </div>
                        <p class="text-gray-300">生成并复制授权令牌</p>
                      </div>
                      <div class="flex items-start space-x-3">
                        <div class="w-6 h-6 rounded-full bg-blue-500 flex items-center justify-center mt-0.5 flex-shrink-0">
                          <i class="fa fa-check text-xs"></i>
                        </div>
                        <p class="text-gray-300">在TV端粘贴令牌完成授权</p>
                      </div>
                    </div>
                    
                    <div class="pt-2">
                      <button class="w-full bg-gradient-to-r from-blue-600 to-indigo-600 hover:from-blue-700 hover:to-indigo-700 text-white py-3 rounded-xl font-medium text-lg transition-all duration-300 transform hover:translate-y-[-2px] hover:shadow-lg hover:shadow-blue-500/20">
                        <i class="fa fa-key mr-2"></i> 立即获取授权令牌
                      </button>
                    </div>
                  </div>
                </div>
              </div>
            </a-card>
          </NuxtLink>
        </div>
      </div>
    </main>

    <!-- 页脚 -->
    <footer class="w-full py-6 px-4 bg-gray-900/80 border-t border-gray-800">
      <div class="max-w-7xl mx-auto text-center text-gray-400 text-sm">
        <p>© 2023 ToolKit 工具箱 | 为您的数字生活提供便捷工具</p>
        <div class="flex justify-center space-x-4 mt-3">
          <a href="#" class="hover:text-white transition-colors duration-200">
            <i class="fa fa-github"></i>
          </a>
          <a href="#" class="hover:text-white transition-colors duration-200">
            <i class="fa fa-twitter"></i>
          </a>
          <a href="#" class="hover:text-white transition-colors duration-200">
            <i class="fa fa-linkedin"></i>
          </a>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
const tools = [
 {
    id: 1,
    title: '阿里云盘TV授权',
    description: '获取阿里云盘TV端的授权令牌',
    path: '/alipan-tv-token',
    available: true
  },
];
</script>

<style scoped>
/* 自定义滚动条 */
::-webkit-scrollbar {
  width: 6px;
  height: 6px;
}

::-webkit-scrollbar-track {
  background: rgba(156, 163, 175, 0.1);
  border-radius: 3px;
}

::-webkit-scrollbar-thumb {
  background: rgba(156, 163, 175, 0.3);
  border-radius: 3px;
}

::-webkit-scrollbar-thumb:hover {
  background: rgba(156, 163, 175, 0.5);
}

/* 动画效果 */
@keyframes float {
  0% { transform: translateY(0px); }
  50% { transform: translateY(-10px); }
  100% { transform: translateY(0px); }
}

.floating {
  animation: float 6s ease-in-out infinite;
}

/* 背景粒子效果 */
.particle {
  position: absolute;
  background-color: rgba(59, 130, 246, 0.2);
  border-radius: 50%;
  animation: float 8s ease-in-out infinite;
}
</style>
    
