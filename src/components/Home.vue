<!-----
  @author KMMoonlight
  @date 2020/9/15 20:43
--->

<template>
    <div class="navigator-wrapper">
        <div class="navigator-sidebar">
            <div class="navigator-title">
                KMMoonlight的导航页
            </div>
            <div class="navigator-description">
                做简单的导航页
            </div>
            <div class="navigator-category">
                <div v-for="item in siteCategories" :key="item.category_id" @click="jumpToCategory(item.category_id)" class="category-style">
                    {{ item.category_name }}
                </div>
            </div>
        </div>
        <div class="navigator-content">
            <div v-for="item in siteCategories" :key="item.category_id" :id="item.category_id">
                <card-group :CardGroup="item"></card-group>
            </div>
        </div>
    </div>
</template>

<script>
    const siteConfig = require("@/website.js")
    import CardGroup from "@/components/CardGroup.vue";

    export default {
        name: "Home",
        components: {
            CardGroup
        },
        data: function() {
            return {
                siteCategories: siteConfig.websiteConfig.data.site_category
            }
        },
        methods: {
            jumpToCategory: function(category) {
                document.getElementById(category).scrollIntoView({
                    behavior: "smooth",
                    block: "start"
                })
            },
        },
    }
</script>

<style scoped>
    .navigator-wrapper {
        display: flex;
        height: 100%;
    }

    .navigator-sidebar {
        width: 300px;
        background: black;
        height: 100%;
    }

    .navigator-content {
        width: 100%;
        overflow: auto;
        background-color: #E9E9E9;
    }

    .navigator-content::-webkit-scrollbar {
        width: 4px;
        /*height: 4px;*/
    }
    .navigator-content::-webkit-scrollbar-thumb {
        border-radius: 10px;
        -webkit-box-shadow: inset 0 0 5px rgba(0,0,0,0.2);
        background: rgba(0,0,0,0.2);
    }
    .navigator-content::-webkit-scrollbar-track {
        -webkit-box-shadow: inset 0 0 5px rgba(0,0,0,0.2);
        border-radius: 0;
        background: rgba(0,0,0,0.1);

    }

    .navigator-title {
        color: white;
        font-size: 20px;
        width: 100%;
        text-align: center;
        margin-top: 20px;
        font-family: "Cascadia Code PL", "Microsoft YaHei UI", Consolas, serif;
    }
    .navigator-description {
        color: white;
        font-size: 12px;
        width: 100%;
        text-align: center;
        margin-top: 20px;
        font-family: "Cascadia Code PL", "Microsoft YaHei UI", Consolas, serif;
    }
    .category-style {
        width: 100%;
        text-align: center;
        font-size: 16px;
        color: #9e9e9e;
        height: 80px;
        line-height: 80px;
        list-style-type: none;
    }
    .category-style:hover {
        font-size: 18px;
        color: white;
        background-color: #9e9e9e;
    }
    .navigator-category {
        margin-top: 20px;
    }
</style>