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
            <div class="max-w-3xl mx-auto w-full">
                <slot />
            </div>
        </a-layout-content>

        <a-layout-footer style="text-align: center">
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
/* 全局深蓝色主题 */
:root {
  --primary-blue: #001529;
  --secondary-blue: #1890ff;
  --light-blue: #e6f7ff;
}

.layout {
    min-height: 100vh;
    background-color: var(--light-blue);
}

.header {
    position: fixed;
    z-index: 1;
    width: 100%;
    background-color: var(--primary-blue);
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
    align-items: flex-start;
    padding-top: 24px;
}

:deep(.ant-layout-header) {
    padding: 0;
}

:deep(.ant-menu) {
    border-bottom: none;
}

/* 为内容区域内的卡片添加样式 */
:deep(.ant-card) {
    width: 100%;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
    border-radius: 8px;
}

:deep(.ant-card-head) {
    background-color: var(--primary-blue);
    color: white;
}

:deep(.ant-card-head-title) {
    color: white;
}

:deep(.ant-btn-primary) {
    background-color: var(--secondary-blue);
    border-color: var(--secondary-blue);
}

:deep(.ant-btn-primary:hover) {
    background-color: #40a9ff;
    border-color: #40a9ff;
}

:deep(.ant-btn-link) {
    color: var(--secondary-blue);
}

:deep(.ant-btn-link:hover) {
    color: #40a9ff;
}
</style>
