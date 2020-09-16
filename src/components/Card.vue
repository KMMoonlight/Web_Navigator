<!-----
  @author KMMoonlight
  @date 2020/9/15 21:42
--->

<template>
    <div class="card-wrapper" @click="jumpToUrl">
        <div class="card-content">
            <img :src="card_content.site_icon" alt="" class="card-img"/>
            <div class="card-title">
                {{card_content.site_title}}
            </div>
        </div>

        <div class="card-description">
            {{card_content.site_description}}
        </div>
    </div>
</template>

<script>
    export default {
        name: "Card",
        props: {
            card_content: Object
        },
        methods: {
            jumpToUrl: function() {
                location.href = this.card_content.site_target_url
            }
        }
    }
</script>

<style scoped>
    .card-wrapper {
        border-radius: 10px;
        width: 240px;
        height: 120px;
        background-color: white;
        margin-left: 40px;
        margin-top: 10px;
    }
    .card-wrapper:hover {
        cursor: pointer;
        box-shadow: 0 2px 2px #9e9e9e;
    }
    .card-title {
        width: 100%;
        font-size: 16px;
        font-weight: bold;
        color: black;
        height: 30px;
        line-height: 30px;
        font-family: "Cascadia Code PL", "Microsoft YaHei UI", Consolas, serif;
    }

    .card-img {
        margin: 10px;
        height: 30px;
        width: 30px;
    }

    .card-content {
        height: 40px;
        display: flex;
        align-items: center;
        padding-top: 10px;
    }

    .card-description {
        margin-right: 10px;
        overflow: hidden;
        margin-left: 10px;
        font-size: 12px;
        color: #9e9e9e;
        height: 80px;
        font-family: "Cascadia Code PL", "Microsoft YaHei UI", Consolas, serif;
    }
</style>