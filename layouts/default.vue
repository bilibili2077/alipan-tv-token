<template>
  <Loading />
  <a-layout class="layout">
    <a-layout-header class="header">
      <div class="header-content max-w-5xl mx-auto px-4 flex items-center justify-between">
        <NuxtLink to="/" class="logo flex items-center space-x-2">
          <div class="w-8 h-8 rounded-md bg-gradient-to-br from-blue-500 to-purple-600 flex items-center justify-center">
            <AimOutlined class="text-white" />
          </div>
          <a-typography-title :level="4" class="!mb-0 !text-white">阿里TV工具箱</a-typography-title>
        </NuxtLink>
        
        <!-- 桌面端导航菜单 -->
        <div class="hidden md:flex items-center space-x-6">
          <a-typography-link to="/" class="text-white hover:text-blue-400 transition-colors">首页</a-typography-link>
          <a-typography-link to="/tools" class="text-white hover:text-blue-400 transition-colors">工具集</a-typography-link>
          <a-typography-link to="/docs" class="text-white hover:text-blue-400 transition-colors">文档</a-typography-link>
          <a-typography-link to="/about" class="text-white hover:text-blue-400 transition-colors">关于</a-typography-link>
        </div>
        
        <!-- 移动端菜单按钮 -->
        <div class="md:hidden">
          <a-button 
            type="text" 
            class="text-white hover:text-blue-400"
            @click="mobileMenuOpen = true"
          >
            <MenuOutlined />
          </a-button>
        </div>
      </div>
    </a-layout-header>

    <a-layout-content class="site-layout-content">
      <div class="max-w-5xl mx-auto w-full px-4 py-8">
        <slot />
      </div>
    </a-layout-content>

    <a-layout-footer class="footer">
      <div class="max-w-5xl mx-auto flex flex-col md:flex-row justify-between items-center">
        <div class="mb-4 md:mb-0">
          <a-typography-text class="text-gray-400">© 2023 阿里TV工具箱</a-typography-text>
        </div>
        <div class="flex space-x-6">
          <a-typography-link href="https://github.com/orgs/OpenListTeam/discussions/15" target="_blank" class="text-gray-400 hover:text-white transition-colors">
            <template #icon>
              <GithubOutlined />
            </template>
            GitHub
          </a-typography-link>
          <a-typography-link href="#" target="_blank" class="text-gray-400 hover:text-white transition-colors">
            <template #icon>
              <QuestionCircleOutlined />
            </template>
            帮助
          </a-typography-link>
          <a-typography-link href="#" target="_blank" class="text-gray-400 hover:text-white transition-colors">
            <template #icon>
              <FileTextOutlined />
            </template>
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
    :width="240"
  >
    <a-menu mode="vertical">
      <a-menu-item key="home" @click="mobileMenuOpen = false">
        <HomeOutlined />
        <span>首页</span>
      </a-menu-item>
      <a-menu-item key="tools" @click="mobileMenuOpen = false">
        <ToolOutlined />
        <span>工具集</span>
      </a-menu-item>
      <a-menu-item key="docs" @click="mobileMenuOpen = false">
        <FileTextOutlined />
        <span>文档</span>
      </a-menu-item>
      <a-menu-item key="about" @click="mobileMenuOpen = false">
        <UserOutlined />
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
  background: linear-gradient(135deg, #1a1a1a 0%, #2e2e2e 100%);
}

.header {
  position: fixed;
  z-index: 100;
  width: 100%;
  background: rgba(30, 30, 30, 0.8);
  backdrop-filter: blur(8px);
  border-bottom: 1px solid rgba(255, 255, 255, 0.05);
  transition: all 0.3s ease;
}

.header:hover {
  background: rgba(30, 30, 30, 0.9);
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
}

.main-card {
  width: 100%;
  max-width: 400px;
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(255, 255, 255, 0.15);
  backdrop-filter: blur(10px);
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.37);
  border-radius: 16px;
  color: #fff;
  transition: all 0.3s ease;
}

.main-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 12px 40px rgba(0, 0, 0, 0.45);
}

.main-card .ant-card-head-title {
  color: #fff;
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
  background: #1a1a1a;
  color: white;
}

:deep(.ant-drawer-header) {
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  color: white;
}

:deep(.ant-drawer-title) {
  color: white;
}

:deep(.ant-menu-dark) {
  background: #1a1a1a;
}
</style>
