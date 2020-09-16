<!-----
  @author KMMoonlight
  @date 2020/9/15 21:51
--->

<template>
    <div>
        <div class="category-title">
           <div class="category-indicator"></div>
           <div class="category-title-content">
               {{ CardGroup.category_name }}
           </div>
        </div>
        <div class="category-content">
            <div v-for="item in CardGroup.site_list" :key="item.title">
                <card :card_content="item"></card>
            </div>
        </div>
    </div>
</template>

<script>
    import Card from '@/components/Card.vue'
    export default {
        name: "CardGroup",
        components: {
            Card
        },
        props: {
            CardGroup: Object
        }
    }
</script>

<style scoped>
    .category-indicator {
        height: 30px;
        width: 10px;
        border-radius: 2px;
        background-color: cornflowerblue;
        line-height: 30px;
    }

    .category-title {
        margin-left: 10px;
        padding-top: 20px;
        height: 30px;
        display: flex;
    }

    .category-title-content {
        color: #9e9e9e;
        line-height: 30px;
        margin-left: 10px;
        font-family: "Cascadia Code PL", "Microsoft YaHei UI", Consolas, serif;
    }
    .category-content {
        display: flex;
        flex-wrap: wrap;
    }

</style>