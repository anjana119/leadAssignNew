<template>
    <div class="w-full no-gutter" style="background: white !important; height: auto !important;">
        <div class="vx-row">
            <div class="vx-col w-full sm:w-1/2 md:w-1/2 landingBodyFirstCol" style="padding-top: 100px; padding-left: 350px;">
                <div>
                    <h1 class="mainHeaderContent">
                        Import And Export Prospecting Leads ...
                    </h1>
                </div>
                <div class="bodyTextContentDiv">
                    <span class="bodyTextContent">
                        Build prospecting lists free from dodgy data, bad-fit buyers and low-qualified leads.
                    </span>
                </div>
                <div>
                    <vs-input size="large" class="inputx emailField" placeholder="" />
                    <vs-button color="primary" type="filled" class="emailFieldBtn">Grab 5 Free Leads Now</vs-button>
                </div>
                <div style="display: flex; justify-content: center; width: 100%; position: relative; top: -20px;">
                    <span>
                        or 
                        <span class="anquerTag">Book a Demo</span>
                    </span>
                </div>
                <div style="margin-top: 55px;">
                    <img src="@/assets/images/trustedBy.png" alt="content-img" class="responsive" style="width: 450px; height: 120px;">
                </div>
            </div>
            <div class="vx-col w-full sm:w-1/2 md:w-1/2" style="padding-top: 50px;">
                <img src="@/assets/images/landingRightImage.png" alt="content-img" class="responsive" style="height: 100%;">
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        components: {},
        data() {
            return {}
        },
        created() {},
        methods: {}
    }
</script>

<style>
    .mainHeaderContent {
        color: #091D30;
        font-family: "Gilroy",Sans-serif;
        font-size: 54px;
        font-weight: 700;
        line-height: 70px;
    }
    .bodyTextContent {
        color: #69727A;
        font-size: 18px;
    }
    .bodyTextContentDiv {
        margin: 30px 0px 30px 2px;
    }
    .emailField {
        background-color: rgb(255, 255, 255);
        border-color: rgb(222, 232, 235);
        border-width: 1px;
        border-radius: 5px;
        height: 72px;
        font-size: 18px;
        min-height: 59px;
        padding: 7px 20px;
        width: 100%;
        max-width: 100%;
        border: 1px solid #e2e2e2;
    }
    [dir] .vs-input--input.large {
        border: none !important;
        box-shadow: none !important;
    }
    .emailFieldBtn {
        float: right;
        position: relative;
        bottom: 60px;
        right: 15px;
        padding: 15px 40px 15px 40px !important;
    }
    .anquerTag {
        cursor: pointer;
        text-decoration: underline;
        font-family: "Gilroy",Sans-serif;
        color: #69727A;

    }
    .anquerTag:hover {
        font-size: 15px;
        font-weight: 500;
    }
</style>

