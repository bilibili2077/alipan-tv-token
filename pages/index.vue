<template>
  <main class="min-h-screen bg-gradient-to-br from-gray-50 to-gray-100 p-4 md:p-8">
    <div class="container mx-auto max-w-3xl">
      <h1 class="text-[clamp(1.8rem,5vw,2.5rem)] font-bold text-gray-800 mb-8 text-center tracking-tight">
        实用工具箱
      </h1>
      
      <div class="grid grid-cols-1 gap-6">
        <ToolCard v-for="tool in tools" :key="tool.id" :tool="tool" />
      </div>
    </div>
  </main>
</template>

<script setup>
import { ref } from 'vue';

// 工具数据 - 仅保留阿里云盘TV授权
const tools = ref([
  {
    id: 1,
    title: '阿里云盘TV授权',
    description: '获取阿里云盘TV端的授权令牌',
    path: '/alipan-tv-token',
    available: true,
    icon: 'cloud'
  }
]).value;

// 工具卡片组件
const ToolCard = {
  props: {
    tool: {
      type: Object,
      required: true
    }
  },
  template: `
    <div 
      :class="[
        'bg-white rounded-xl shadow-md hover:shadow-xl transition-all duration-300 overflow-hidden',
        tool.available ? 'hover:scale-[1.02] cursor-pointer' : 'opacity-70 cursor-not-allowed'
      ]"
    >
      <div class="p-6">
        <div class="flex items-start gap-4">
          <div class="flex-shrink-0 w-12 h-12 rounded-lg bg-blue-100 flex items-center justify-center">
            <i class="fa fa-{{ tool.icon }} text-blue-600 text-xl"></i>
          </div>
          <div>
            <h3 class="text-xl font-semibold text-gray-800 mb-2">
              {{ tool.title }}
            </h3>
            <p class="text-gray-600 text-sm leading-relaxed">
              {{ tool.description }}
            </p>
          </div>
        </div>
      </div>
      <div class="h-1 bg-gradient-to-r from-blue-500 to-indigo-600"></div>
    </div>
  `
};
</script>

<style scoped>
/* 全局样式 */
:root {
  --transition: all 0.3s ease;
}

/* 工具卡片样式 */
.ToolCard {
  transition: var(--transition);
}

.ToolCard:hover {
  transform: translateY(-5px);
}

.ToolCard .card-title {
  transition: var(--transition);
}

.ToolCard:hover .card-title {
  color: #3b82f6;
}
</style>
