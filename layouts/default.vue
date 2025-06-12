<template>
  <Loading />
  <a-layout class="layout">
    <a-layout-header class="header">
      <div class="header-content max-w-5xl mx-auto px-4 flex items-center justify-center">
        <NuxtLink to="/" class="logo flex items-center space-x-2">
          <div class="w-8 h-8 rounded-md bg-gradient-to-br from-blue-500 to-purple-600 flex items-center justify-center shadow-lg shadow-blue-500/20">
            <AimOutlined class="text-white" />
          </div>
          <a-typography-title :level="4" class="!mb-0 !text-white">阿里TV工具箱</a-typography-title>
        </NuxtLink>
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
</template>

<script setup>
import { 
  GithubOutlined, 
  QuestionCircleOutlined,
  FileTextOutlined,
  AimOutlined
} from '@ant-design/icons-vue'
import Loading from '~/components/Loading.vue'
</script>

<style scoped>
.layout {
  min-height: 100vh;
}

.header {
  position: fixed;
  z-index: 100;
  width: 100%;
  backdrop-filter: blur(12px);
  border-bottom: 1px solid rgba(59, 130, 246, 0.1);
  transition: all 0.3s ease;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
}

.header:hover {
  box-shadow: 0 6px 24px rgba(0, 0, 0, 0.25);
}

.header-content {
  height: 64px;
  justify-content: center !important;
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
  border: 1px solid rgba(59, 130, 246, 0.15);
  backdrop-filter: blur(20px);
  box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5), 
              0 5px 15px rgba(59, 130, 246, 0.05);
  border-radius: 24px;
  color: #e2e8f0;
  transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
  overflow: hidden;
}

.main-card:hover {
  transform: translateY(-10px) scale(1.02);
  box-shadow: 0 20px 45px rgba(0, 0, 0, 0.6), 
              0 8px 25px rgba(59, 130, 246, 0.1);
  border-color: rgba(59, 130, 246, 0.25);
}

.main-card .ant-card-head {
  border-bottom: 1px solid rgba(59, 130, 246, 0.08);
  padding: 16px 24px;
  border-top-left-radius: 24px;
  border-top-right-radius: 24px;
}

.main-card .ant-card-head-title {
  color: #f8fafc;
  font-weight: 600;
  letter-spacing: 0.5px;
}

.main-card .ant-card-body {
  padding: 24px;
}

.footer {
  text-align: center;
  color: #94a3b8;
  padding: 24px 0;
  border-top: 1px solid rgba(59, 130, 246, 0.05);
}

/* 深度选择器覆盖 Ant Design 样式 */
:deep(.ant-layout-header) {
  padding: 0;
}

:deep(.ant-menu) {
  border-bottom: none;
}

/* 移除装饰元素 */
.bg-grid, .bg-gradient {
  display: none;
}
</style>
