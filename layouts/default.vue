<template>
  <Loading />
  <a-layout class="layout">
    <a-layout-header class="header">
      <div class="header-content max-w-3xl mx-auto px-4 flex items-center">
        <NuxtLink to="/" class="logo">
          <a-typography-title :level="4" class="!mb-0 !text-white">阿里TV工具箱</a-typography-title>
        </NuxtLink>
      </div>
    </a-layout-header>

    <a-layout-content class="site-layout-content">
      <div class="max-w-3xl mx-auto w-full flex justify-center items-center min-h-[400px]">
        <a-card class="main-card" hoverable>
          <slot />
        </a-card>
      </div>
    </a-layout-content>

    <a-layout-footer class="footer">
      <a-typography-link href="https://github.com/orgs/OpenListTeam/discussions/15" target="_blank">
        <template #icon>
          <GithubOutlined />
        </template>
        GitHub
      </a-typography-link>
    </a-layout-footer>
  </a-layout>
</template>

<script setup>
import { GithubOutlined } from '@ant-design/icons-vue'
import Loading from '~/components/Loading.vue'
</script>

<style scoped>
.layout {
  min-height: 100vh;
  background: linear-gradient(135deg, #1a1a1a 0%, #2e2e2e 100%);
}

.header {
  position: fixed;
  z-index: 1;
  width: 100%;
  background: transparent;
  backdrop-filter: blur(8px);
}

.header-content {
  height: 64px;
}

.logo {
  float: left;
  height: 31px;
  margin: 16px 0;
}

.site-layout-content {
  padding: 0 24px;
  margin-top: 64px;
  min-height: calc(100vh - 64px - 70px);
  display: flex;
  justify-content: center;
  align-items: center;
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
}

.main-card .ant-card-head-title {
  color: #fff;
}

.footer {
  text-align: center;
  background: transparent;
  color: #999;
}

/* 深度选择器覆盖 Ant Design 样式 */
:deep(.ant-layout-header) {
  padding: 0;
}

:deep(.ant-menu) {
  border-bottom: none;
}
</style>
