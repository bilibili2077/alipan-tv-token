<template>

    <head>
        <title>工具箱</title>
    </head>
    <main class="max-h-screen bg-gray-100 p-4">
        <div class="mx-auto w-full max-w-3xl mb-8">
            <div class="space-y-4">
                <template v-for="tool in tools" :key="tool.id">
                    <NuxtLink v-if="tool.available" :to="tool.path" class="block">
                        <a-card hoverable>
                            <template #title>
                                <h2 class="text-xl font-medium"
                                    :class="tool.available ? 'text-gray-800' : 'text-gray-400'">
                                    {{ tool.title }}
                                </h2>
                            </template>
                            <p :class="tool.available ? 'text-gray-600' : 'text-gray-400'">{{ tool.description }}</p>
                        </a-card>
                    </NuxtLink>
                    <a-card v-else hoverable>
                        <template #title>
                            <h2 class="text-xl font-medium text-gray-400">{{ tool.title }}</h2>
                        </template>
                        <p class="text-gray-400">{{ tool.description }}</p>
                    </a-card>
                </template>
            </div>
        </div>
    </main>
</template>

<script setup>
const tools = [
 {
        id: 1,
        title: 'OpenList--阿里云盘TV授权--（此工具完全免费）',
        description: '点击获取阿里云盘TV端的授权令牌--(失效了或者有问题请私聊TG机器人 @eoops_bot )',
        path: '/alipan-tv-token',
        available: true
    },

].sort((a, b) => a.id - b.id);
</script>

<style scoped></style>
