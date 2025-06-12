<template>
    <Loading />
    <div class="min-h-screen bg-gray-50 dark:bg-gray-900 transition-colors duration-300">
        <!-- 现代化导航栏 -->
        <header class="fixed top-0 left-0 right-0 z-50 bg-white dark:bg-gray-800 shadow-md transition-all duration-300">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="flex justify-between h-16">
                    <div class="flex items-center">
                        <NuxtLink to="/" class="flex items-center">
                            <span class="text-xl font-bold bg-gradient-to-r from-blue-600 to-indigo-600 bg-clip-text text-transparent">
                                阿里TV工具箱
                            </span>
                        </NuxtLink>
                    </div>
                    <div class="flex items-center">
                        <button id="theme-toggle" class="p-2 rounded-full hover:bg-gray-100 dark:hover:bg-gray-700 transition-colors">
                            <template v-if="isDarkMode">
                                <SunOutlined class="text-yellow-400" />
                            </template>
                            <template v-else>
                                <MoonOutlined class="text-gray-600" />
                            </template>
                        </button>
                    </div>
                </div>
            </div>
        </header>

        <!-- 主要内容区域 -->
        <main class="pt-20 pb-16 px-4 sm:px-6 lg:px-8 max-w-3xl mx-auto">
            <slot />
        </main>

        <!-- 页脚 -->
        <footer class="bg-white dark:bg-gray-800 border-t border-gray-200 dark:border-gray-700">
            <div class="max-w-7xl mx-auto py-6 px-4 sm:px-6 lg:px-8">
                <div class="flex justify-center items-center">
                    <a-typography-link 
                        href="https://github.com/orgs/OpenListTeam/discussions/15" 
                        target="_blank"
                        class="flex items-center text-gray-600 dark:text-gray-300 hover:text-blue-600 dark:hover:text-blue-400 transition-colors"
                    >
                        <GithubOutlined class="mr-2" />
                        GitHub
                    </a-typography-link>
                </div>
            </div>
        </footer>
    </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import { GithubOutlined, SunOutlined, MoonOutlined } from '@ant-design/icons-vue'
import Loading from '~/components/Loading.vue'

// 深色模式状态
const isDarkMode = ref(false)

// 检查系统或本地存储的主题偏好
onMounted(() => {
    if (localStorage.theme === 'dark' || (!('theme' in localStorage) && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
        document.documentElement.classList.add('dark')
        isDarkMode.value = true
    } else {
        document.documentElement.classList.remove('dark')
        isDarkMode.value = false
    }
    
    // 监听主题切换按钮点击事件
    const themeToggle = document.getElementById('theme-toggle')
    themeToggle.addEventListener('click', toggleTheme)
})

// 切换主题
const toggleTheme = () => {
    if (isDarkMode.value) {
        document.documentElement.classList.remove('dark')
        localStorage.theme = 'light'
    } else {
        document.documentElement.classList.add('dark')
        localStorage.theme = 'dark'
    }
    isDarkMode.value = !isDarkMode.value
}
</script>

<style scoped>
/* 全局过渡动画 */
body {
    transition: background-color 0.3s ease;
}

/* 导航栏滚动效果 */
header {
    transition: all 0.3s ease;
}

header.scrolled {
    background-color: rgba(255, 255, 255, 0.95);
    -webkit-backdrop-filter: blur(8px);
    backdrop-filter: blur(8px);
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
}

.dark header.scrolled {
    background-color: rgba(31, 41, 55, 0.95);
    -webkit-backdrop-filter: blur(8px);
    backdrop-filter: blur(8px);
}

/* 按钮悬停效果 */
button {
    transition: all 0.2s ease;
}

button:hover {
    transform: translateY(-1px);
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
}

button:active {
    transform: translateY(0);
    box-shadow: none;
}
</style>
    
