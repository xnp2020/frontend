<template>
    <h3>Key管理状态</h3>
    <div v-for="item in result" :key="item.id" class="image-container">
        <p>{{ item.title }}</p>
        <img :src="item.avatar" alt="">
    </div>

</template>

<script>
export default {
    data() {
        return {
            result: [
                {
                    "id": 1,
                    "title": "title1",
                    "avatar": "https://oss.cloudhubei.com.cn/cms/release/set1/20240604/66b1f1809845b66e131138d749c6ca2c.png%21styleprocess"
                },
                {
                    "id": 2,
                    "title": "title2",
                    "avatar": "https://img.doooor.com/img/forum/202408/02/100456vhzmzc6h6ifomnmj.jpg"
                },
                {
                    "id": 3,
                    "title": "title3",
                    "avatar": "https://inews.gtimg.com/om_bt/OOlLO3pVVLvGJeAI7UfEqfjSwT7JFNh8afum6-J4pLcE4AA/641"
                },
            ]
        }
    }
}

</script>

<style>
.image-container img {
    max-width: 20%;
    max-height: 20%;
}
</style>