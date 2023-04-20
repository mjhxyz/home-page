<script setup>
import ChatGPTIcon from './icons/IconChatGPT.vue'
import DDGIcon from './icons/IconDDG.vue'
import BlogIcon from './icons/IconBlog.vue'
import PwdIcon from './icons/IconPwd.vue'
</script>

<template>
    <div class="container">
        <div class="page-box">
            <div v-for="link in linkList" :key="link.link" class="page-box-card">
                <a class="page-box-card-a" target="_blank" :href="link.link">
                    <component color="#6F98A8" :is="link.icon" />
                    {{ link.title }}
                </a>
            </div>
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
                    title: 'Blog',
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
                {
                    title: 'PwdGenerator',
                    link: 'https://lls.mjhxyz.top/',
                    icon: PwdIcon,
                }
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
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    align-content: start;
    justify-content: center;
}

@media screen and (min-width: 768px) {
    .page-box .page-box-card {
        flex-basis: 33.33%;
    }
}

@media screen and (max-width: 767px) {
    .page-box .page-box-card {
        flex-basis: 100%;
    }
}


.page-box .page-box-card {
    margin-bottom: 20px;
    height: 120px;
    display: flex;
    justify-content: space-around;
    align-items: center;
    flex-direction: column;
    overflow: hidden;
    padding: 0 10px;
}

.page-box .page-box-card .page-box-card-a {
    border: 1px solid #333;
    height: 100px;
    width: 100%;
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

.page-box .page-box-card::after {
    display: block;
    padding-bottom: calc(33.33% + 10px);
}

.page-box-card-a:hover {
    transform: translateY(-5px);
    box-shadow: 0px 5px 10px rgba(100, 100, 100, 0.5);
    color: hsla(160, 100%, 37%, 1);
}
</style>
