<template>
    <div style="display: flex; justify-content: center;">
        <div class="vx-row" style="margin-bottom: 6%;">
            <div class="vx-col w-full sm:w-1/2 md:w-1/2 firstColForthContent">
                <h1 class="headerContentForthPage">
                    Code Red Safety Closed in New Business Within
                </h1>
                <h3 class="forthContentParagraph">
                    Lorem Ipsum is simply dummy text of the printing an the 1500s, when an unknown printer took a galley
                </h3>
                <span class="linkToView">
                    Call to action
                </span>
            </div>
            <div class="vx-col w-full sm:w-1/2 md:w-1/2">
                <img src="https://mcusercontent.com/122a616be556c3f722865e0cf/images/87ff564a-d867-4a2a-814c-7cfdec215b21.jpeg" alt="image Content" style="width: 100%;" />
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            
        }
    },
}
</script>

<style>
    .headerContentForthPage {
        text-align: left;
        letter-spacing: 0px;
        font: normal normal medium 45px/55px Poppins;
        color: #142537;
        opacity: 1;
        font-size: 40px;
        margin-bottom: 35px;
        padding-left: 25%;
    }
    .forthContentParagraph {
        font: normal normal 300 18px/33px Poppins;
        letter-spacing: 0px;
        color: #142537;
        line-height: 28px;
        padding-left: 25%;
    }
    .actionButtonForthContent {
        float: inherit;
        font-family: 'Poppins', sans-serif;
        background:#FF0000 !important;
        left: 0px;
        right: 15px;
        top: 75px;
        padding: 15px 40px 15px 40px !important;
    }
    .firstColForthContent {
        padding-top: 10% !important;
    }
    .linkToView {
        color: #FF0000;
        text-decoration: underline;
        cursor: pointer;
        font: normal normal medium 22px/33px Poppins;
        line-height: 27px;
        display: flex;
        width: 40%;
        justify-content: flex-start;
        margin-top: 35px;
        padding-left: 25%;
    }
    .linkToView:hover {
        font-weight: 600;
    }
</style>