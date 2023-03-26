<script setup>
import ChatGPTIcon from './icons/IconChatGPT.vue'
import DDGIcon from './icons/IconDDG.vue'
import BlogIcon from './icons/IconBlog.vue'
</script>

<template>
    <div class="container">
        <div class="page-box">
            <a target="_blank" :href="link.link" v-for="link in linkList" :key="link.link" class="page-box-card">
                <component color="#6F98A8" :is="link.icon" />
                {{ link.title }}
            </a>
        </div>
    </div>
</template>

<script>
export default {
    name: 'NavRect',
    data() {
        return {
            linkList: [
                {
                    title: '博客',
                    link: 'https://blog.mjhxyz.top',
                    icon: BlogIcon,
                },
                {
                    title: 'ChatGPT',
                    link: 'https://chat.mjhxyz.top',
                    icon: ChatGPTIcon,
                },
                {
                    title: 'DDG',
                    link: 'https://ddg.mjhxyz.top',
                    icon: DDGIcon,
                },
            ]
        }
    }
}
</script>

<style scoped>
.container {
    width: 680px;
    /* border: 1px solid #000; */
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;
}

.page-box {
    /* border: 1px solid #000; */
    min-height: 300px;
    width: 500px;
    display: flex;
    flex-wrap: wrap;
    align-content: start;
    justify-content: space-between;
}

.page-box .page-box-card {
    border: 1px solid #333;
    width: 150px;
    height: 100px;
    margin-bottom: 30px;
    border-radius: 10px;
    display: flex;
    justify-content: space-around;
    align-items: center;
    flex-direction: column;
    cursor: pointer;
    box-shadow: 0px 2px 5px rgba(100, 100, 100, 0.3);
    overflow: hidden;
    transition: all 0.3s ease-in-out;
    color: #fff;
    background: hsl(248, 21%, 13%);
    padding: 10px 0;
}

.page-box-card:hover {
    transform: translateY(-5px);
    box-shadow: 0px 5px 10px rgba(100, 100, 100, 0.5);
    color: hsla(160, 100%, 37%, 1);
}
</style>
