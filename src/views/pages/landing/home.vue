<template>
    <div class="" style="background: white !important; height: auto !important;">
        <homePageFirstContent style="padding-top: 30px;" />
        <vs-divider class="dividerClass" />
        <homePageSecondContent />
        <vs-divider class="dividerClass" />
        <homePageThirdContent />
        <homePageForthContent />
        <homePageFifthContent style="position: relative; bottom: 980px;" />
    </div>
</template>

<script>
    import homePageFirstContent from "@/components/landingPage/homePageFirstContent.vue";
    import homePageSecondContent from "@/components/landingPage/homePageSecondContent.vue";
    import homePageThirdContent from "@/components/landingPage/homePageThirdContent.vue";
    import homePageForthContent from "@/components/landingPage/homePageForthContent.vue";
    import homePageFifthContent from "@/components/landingPage/homePageFifthContent.vue";
    export default {
        components: {
            homePageFirstContent,
            homePageSecondContent,
            homePageThirdContent,
            homePageForthContent,
            homePageFifthContent
        },
        data() {
            return {}
        },
        created() {},
        methods: {}
    }
</script>

<style>
    .dividerClass {
        margin-bottom: 6%;
        margin-top: 6%;
        width: 98%;
        margin-left: 16px;
    }
</style>
