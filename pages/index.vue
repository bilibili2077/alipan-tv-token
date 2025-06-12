<template>
    <div class="min-h-screen flex flex-col">
        <!-- 主内容区 -->
        <main class="flex-1 flex items-center justify-center p-4 pt-12 pb-12">
            <div class="container mx-auto max-w-3xl">
                <div class="flex flex-col items-center justify-center min-h-[calc(100vh-12rem)]">
                    <!-- 卡片 -->
                    <div class="w-full max-w-md bg-white dark:bg-gray-800 rounded-2xl shadow-xl overflow-hidden transition-all duration-300 hover:shadow-2xl transform hover:-translate-y-1">
                        <div class="p-6 md:p-8">
                            <div class="flex items-center mb-4">
                                <div class="w-12 h-12 bg-blue-100 dark:bg-blue-900 rounded-xl flex items-center justify-center">
                                    <svg class="w-6 h-6 text-blue-600 dark:text-blue-400" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2m-3 7h3m-3 4h3m-6-4h.01M9 16h.01"></path>
                                    </svg>
                                </div>
                                <h2 class="ml-4 text-2xl font-bold text-gray-800 dark:text-white">阿里云盘TV授权</h2>
                            </div>
                            <p class="text-gray-600 dark:text-gray-300 mb-6">获取阿里云盘TV端的授权令牌，轻松不限速访问您的云盘资源。</p>
                            <div class="flex justify-center">
                                <NuxtLink to="/alipan-tv-token" class="w-full bg-blue-600 hover:bg-blue-700 text-white font-medium py-3 px-6 rounded-xl transition-all duration-300 flex items-center justify-center">
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
        <footer class="py-4 px-6 border-t border-gray-200 dark:border-gray-700">
            <div class="container mx-auto text-center text-sm text-gray-500 dark:text-gray-400">
                <p>© 2025 阿里工具箱 | 让你的工作更高效</p>
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
</style>
