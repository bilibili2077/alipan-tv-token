<template>
  <Loading />
  <a-layout class="layout">
    <a-layout-header class="header">
      <div class="header-content max-w-5xl mx-auto px-4 flex items-center justify-between">
        <NuxtLink to="/" class="logo flex items-center space-x-2">
          <div class="w-8 h-8 rounded-md bg-gradient-to-br from-blue-500 to-purple-600 flex items-center justify-center shadow-lg shadow-blue-500/20">
            <AimOutlined class="text-white" />
          </div>
          <a-typography-title :level="4" class="!mb-0 !text-white">阿里TV工具箱</a-typography-title>
        </NuxtLink>
        
        <!-- 桌面端导航菜单 -->
        <div class="hidden md:flex items-center space-x-6">
          <a-typography-link to="/" class="text-white hover:text-blue-400 transition-all duration-300 flex items-center">
            <HomeOutlined class="mr-1" />
            首页
          </a-typography-link>
          <a-typography-link to="/tools" class="text-white hover:text-blue-400 transition-all duration-300 flex items-center">
            <ToolOutlined class="mr-1" />
            工具集
          </a-typography-link>
          <a-typography-link to="/docs" class="text-white hover:text-blue-400 transition-all duration-300 flex items-center">
            <FileTextOutlined class="mr-1" />
            文档
          </a-typography-link>
          <a-typography-link to="/about" class="text-white hover:text-blue-400 transition-all duration-300 flex items-center">
            <UserOutlined class="mr-1" />
            关于
          </a-typography-link>
        </div>
        
        <!-- 移动端菜单按钮 -->
        <div class="md:hidden">
          <a-button 
            type="text" 
            class="text-white hover:text-blue-400 hover:bg-white/10 rounded-full p-2 transition-all duration-300"
            @click="mobileMenuOpen = true"
          >
            <MenuOutlined />
          </a-button>
        </div>
      </div>
    </a-layout-header>

    <a-layout-content class="site-layout-content">
      <div class="max-w-5xl mx-auto w-full px-4 py-8 flex justify-center items-center min-h-[calc(100vh-134px)]">
        <div class="w-full max-w-2xl">
          <slot />
        </div>
      </div>
    </a-layout-content>

    <a-layout-footer class="footer">
      <div class="max-w-5xl mx-auto flex flex-col md:flex-row justify-between items-center">
        <div class="mb-4 md:mb-0">
          <a-typography-text class="text-gray-400">© 2023 阿里TV工具箱</a-typography-text>
        </div>
        <div class="flex space-x-6">
          <a-typography-link href="https://github.com/orgs/OpenListTeam/discussions/15" target="_blank" class="text-gray-400 hover:text-white transition-all duration-300 flex items-center">
            <GithubOutlined class="mr-1" />
            GitHub
          </a-typography-link>
          <a-typography-link href="#" target="_blank" class="text-gray-400 hover:text-white transition-all duration-300 flex items-center">
            <QuestionCircleOutlined class="mr-1" />
            帮助
          </a-typography-link>
          <a-typography-link href="#" target="_blank" class="text-gray-400 hover:text-white transition-all duration-300 flex items-center">
            <FileTextOutlined class="mr-1" />
            隐私政策
          </a-typography-link>
        </div>
      </div>
    </a-layout-footer>
  </a-layout>
  
  <!-- 移动端侧边菜单 -->
  <a-drawer
    title="菜单"
    :visible="mobileMenuOpen"
    @close="mobileMenuOpen = false"
    placement="right"
    :width="280"
    class="modern-drawer"
  >
    <a-menu mode="vertical" class="drawer-menu">
      <a-menu-item key="home" @click="mobileMenuOpen = false">
        <HomeOutlined class="mr-2" />
        <span>首页</span>
      </a-menu-item>
      <a-menu-item key="tools" @click="mobileMenuOpen = false">
        <ToolOutlined class="mr-2" />
        <span>工具集</span>
      </a-menu-item>
      <a-menu-item key="docs" @click="mobileMenuOpen = false">
        <FileTextOutlined class="mr-2" />
        <span>文档</span>
      </a-menu-item>
      <a-menu-item key="about" @click="mobileMenuOpen = false">
        <UserOutlined class="mr-2" />
        <span>关于</span>
      </a-menu-item>
    </a-menu>
  </a-drawer>
</template>

<script setup>
import { ref } from 'vue'
import { 
  GithubOutlined, 
  MenuOutlined, 
  HomeOutlined, 
  ToolOutlined, 
  FileTextOutlined, 
  UserOutlined, 
  QuestionCircleOutlined,
  AimOutlined
} from '@ant-design/icons-vue'
import Loading from '~/components/Loading.vue'

// 移动端菜单状态
const mobileMenuOpen = ref(false)
</script>

<style scoped>
.layout {
  min-height: 100vh;
  background: linear-gradient(135deg, #121212 0%, #222222 100%);
  background-attachment: fixed;
}

.header {
  position: fixed;
  z-index: 100;
  width: 100%;
  background: rgba(20, 20, 20, 0.95);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.08);
  transition: all 0.3s ease;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
}

.header:hover {
  background: rgba(20, 20, 20, 0.98);
  box-shadow: 0 6px 24px rgba(0, 0, 0, 0.25);
}

.header-content {
  height: 64px;
}

.logo {
  display: flex;
  align-items: center;
}

.site-layout-content {
  padding: 0;
  margin-top: 64px;
  min-height: calc(100vh - 64px - 70px);
  display: flex;
  justify-content: center;
  align-items: center;
}

.main-card {
  width: 100%;
  max-width: 480px;
  background: rgba(30, 30, 30, 0.9);
  border: 1px solid rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(20px);
  box-shadow: 0 15px 35px rgba(0, 0, 0, 0.4), 
              0 5px 15px rgba(0, 0, 0, 0.2);
  border-radius: 20px;
  color: #fff;
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  overflow: hidden;
}

.main-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(135deg, rgba(255, 255, 255, 0.05) 0%, transparent 50%);
  pointer-events: none;
  z-index: 1;
}

.main-card:hover {
  transform: translateY(-10px) scale(1.02);
  box-shadow: 0 20px 45px rgba(0, 0, 0, 0.5), 
              0 8px 25px rgba(0, 0, 0, 0.25);
}

.main-card .ant-card-head {
  border-bottom: 1px solid rgba(255, 255, 255, 0.05);
  padding: 16px 24px;
}

.main-card .ant-card-head-title {
  color: #fff;
  font-weight: 600;
  letter-spacing: 0.5px;
}

.main-card .ant-card-body {
  padding: 24px;
}

.footer {
  text-align: center;
  background: transparent;
  color: #999;
  padding: 24px 0;
  border-top: 1px solid rgba(255, 255, 255, 0.05);
}

/* 深度选择器覆盖 Ant Design 样式 */
:deep(.ant-layout-header) {
  padding: 0;
}

:deep(.ant-menu) {
  border-bottom: none;
}

:deep(.ant-drawer-content) {
  background: rgba(20, 20, 20, 0.95);
  color: white;
  backdrop-filter: blur(15px);
  border-left: 1px solid rgba(255, 255, 255, 0.08);
}

:deep(.ant-drawer-header) {
  border-bottom: 1px solid rgba(255, 255, 255, 0.08);
  color: white;
  padding: 16px 24px;
}

:deep(.ant-drawer-title) {
  color: white;
  font-weight: 500;
}

:deep(.ant-menu-dark) {
  background: transparent;
}

:deep(.ant-menu-dark .ant-menu-item-selected) {
  background-color: rgba(59, 130, 246, 0.1);
  color: #3b82f6;
}

:deep(.ant-menu-dark .ant-menu-item:hover) {
  color: #3b82f6;
}

:deep(.ant-menu-dark .ant-menu-item::after) {
  border-right-color: #3b82f6;
}

/* 装饰元素 */
.bg-grid {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: radial-gradient(rgba(255, 255, 255, 0.05) 1px, transparent 1px);
  background-size: 40px 40px;
  z-index: -1;
}

.bg-gradient {
  position: fixed;
  top: -50%;
  left: -50%;
  width: 200%;
  height: 200%;
  background: radial-gradient(circle, rgba(59, 130, 246, 0.15) 0%, transparent 70%);
  z-index: -1;
  animation: pulse 20s infinite;
}

@keyframes pulse {
  0%, 100% { transform: scale(1); opacity: 0.5; }
  50% { transform: scale(1.2); opacity: 0.8; }
}
</style>
