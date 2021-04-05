<template>
    <div>
        <vx-card class="mainCardInFifthContent">
            <div class="flex">
                <div class="w-1/4 collInArryFifth" v-for="(item, index) in imageContent" :key="index">
                    <img :src="item.path" alt="image" style="margin-left: auto; margin-right: auto; padding-right: 50px;" />
                    <h1 class="bodyTextInFifthContent">
                        {{item.text}}
                    </h1>
                </div>
            </div>
        </vx-card>
    </div>
</template>

<script>
export default {
    data() {
        return {
            imageContent: [
                {
                    path: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/e69514da-7f1c-43db-ae5c-56cf320e998d.png",
                    text: "Find the right leads for you"
                },
                {
                    path: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/afb1d65a-45a9-40ed-a460-b862cac0be71.png",
                    text: "Get their most important info"
                },
                {
                    path: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/0a80c925-4cbc-475b-beb3-f2ab4c149cc6.png",
                    text: "Find the right leads for you"
                },
                {
                    path: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/e69514da-7f1c-43db-ae5c-56cf320e998d.png",
                    text: "Get their most important info"
                }
            ]
        }
    }
}
</script>

<style>
    .bodyTextInFifthContent {
        width: 60%;
        margin-left: auto;
        margin-right: auto;
        font: normal normal 600 26px/40px Poppins;
        letter-spacing: 0px;
        color: #142537;
        opacity: 1;
    }
    .mainCardInFifthContent {
        width: 80%;
        height: 300px;
        margin-left: auto;
        margin-right: auto;
        border-radius: 0px !important;
    }
    .vx-card .vx-card__collapsible-content.vs-con-loading__container {
        padding-top: 35px;
    }
</style>