<template>
    <div class="min-h-screen bg-gradient-to-br from-blue-900 to-indigo-950 dark:from-blue-950 dark:to-indigo-950 flex flex-col">
        <!-- 主内容区 -->
        <main class="flex-1 flex items-center justify-center p-4 pt-12 pb-12">
            <div class="container mx-auto max-w-3xl">
                <div class="flex flex-col items-center justify-center min-h-[calc(100vh-12rem)]">
                    <!-- 卡片 -->
                    <div class="w-full max-w-md bg-white/10 dark:bg-gray-800/30 backdrop-blur-md rounded-2xl shadow-xl overflow-hidden transition-all duration-300 hover:shadow-2xl transform hover:-translate-y-1 border border-white/20 dark:border-white/10">
                        <div class="p-6 md:p-8">
                            <div class="flex items-center mb-4">
                                <div class="w-12 h-12 bg-blue-600/20 dark:bg-blue-600/20 rounded-xl flex items-center justify-center">
                                    <svg class="w-6 h-6 text-blue-300 dark:text-blue-300" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2m-3 7h3m-3 4h3m-6-4h.01M9 16h.01"></path>
                                    </svg>
                                </div>
                                <h2 class="ml-4 text-2xl font-bold text-white">阿里云盘TV授权</h2>
                            </div>
                            <p class="text-blue-100 dark:text-blue-100 mb-6">获取阿里云盘TV端的授权令牌，轻松在电视上访问您的云盘资源。</p>
                            <div class="flex justify-center">
                                <NuxtLink to="/alipan-tv-token" class="w-full bg-blue-600 hover:bg-blue-700 text-white font-medium py-3 px-6 rounded-xl transition-all duration-300 flex items-center justify-center shadow-lg shadow-blue-600/20">
                                    <span>开始授权</span>
                                    <svg class="ml-2 w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3"></path>
                                    </svg>
                                </NuxtLink>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </main>

        <!-- 页脚 -->
        <footer class="bg-blue-900/50 dark:bg-blue-950/50 backdrop-blur-md py-4 px-6 border-t border-white/10">
            <div class="container mx-auto text-center text-sm text-blue-200 dark:text-blue-200">
                <p>© 2023 工具箱 | 让你的工作更高效</p>
            </div>
        </footer>
    </div>
</template>

<script setup>
import { useHead } from '#app'

// 设置页面标题
useHead({
    title: '阿里云盘TV授权工具 | 工具箱'
})

// 主题切换功能
const toggleTheme = () => {
    if (document.documentElement.classList.contains('dark')) {
        document.documentElement.classList.remove('dark')
        localStorage.theme = 'light'
    } else {
        document.documentElement.classList.add('dark')
        localStorage.theme = 'dark'
    }
}

// 初始化主题
onMounted(() => {
    // 从localStorage获取主题偏好
    if (localStorage.theme === 'dark' || (!('theme' in localStorage) && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
        document.documentElement.classList.add('dark')
    } else {
        document.documentElement.classList.remove('dark')
    }
    
})

// 页面滚动效果
onMounted(() => {

})

// 清理事件监听器
onBeforeUnmount(() => {

})
</script>

<style scoped>
/* 导入Tailwind CSS */
@tailwind base;
@tailwind components;
@tailwind utilities;

/* 自定义动画 */
@keyframes float {
    0% { transform: translateY(0px); }
    50% { transform: translateY(-10px); }
    100% { transform: translateY(0px); }
}

.float-animation {
    animation: float 6s ease-in-out infinite;
}

/* 平滑滚动 */
html {
    scroll-behavior: smooth;
}

/* 全局样式 */
body {
    background-color: theme('colors.blue.900');
}
</style>
    
