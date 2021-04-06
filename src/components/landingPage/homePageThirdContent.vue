<template>
    <div class="mainClassThirdContent">
        <div class="flex">
            <div class="w-2/12"></div>
            <div class="w-8/12">
                <h1 class="mainHeaderThirdContent">
                    AI & human connected data verification & cleaning for the highest accuracy
                </h1>
                <h4 class="bodyTextThirdContent">
                    Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley
                </h4>
                <div>
                    <vs-button class="actionButtonThirdContent" color="danger" type="filled" icon-pack="feather" icon="icon-arrow-up-right" icon-after>
                        Get in touch
                    </vs-button>
                </div>
            </div>
            <div class="w-2/12"></div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {}
    },
}
</script>

<style>
    .mainClassThirdContent {
        display: flex;
        justify-content: center;
        height: 925px;
        background: #142537;
    }
    .mainHeaderThirdContent {
        text-align: center;
        font: normal normal 600 55px/72px Poppins;
        letter-spacing: 0px;
        color: #FFFFFF;
        opacity: 1;
        height: 149px;
        top: 115px;
        position: relative;
        opacity: 1;
        display: flex;
        justify-content: center;
        margin-left: auto;
        margin-right: auto;
    }
    .bodyTextThirdContent {
        text-align: center;
        font: normal normal 300 22px/33px Poppins;
        letter-spacing: 0px;
        color: #FFFFFF;
        opacity: 1;
        width: 65%;
        margin-left: auto;
        margin-right: auto;
        position: relative;
        top: 220px;
    }
    .secondContentParagraph {
        font: normal normal 300 18px/33px Poppins;
        letter-spacing: 0px;
        color: #142537;
        line-height: 28px;
    }
    .actionButtonThirdContent {
        float: inherit;
        font-family: 'Poppins', sans-serif;
        background:#FF0000 !important;
        left: 0px;
        right: 15px;
        top: 75px;
        padding: 15px 40px 15px 40px !important;
        position: relative;
        top: 310px;
        margin-left: auto;
        margin-right: auto;
    }
    @media only screen and (max-width: 1024px) {
        .mainHeaderThirdContent {
            font: normal normal 600 47px/60px Poppins;
            top: 100px;
        }
        .bodyTextThirdContent {
            width: 100%;
            top: 215px;
        }
    }
    @media only screen and (max-width: 768px) {
        .mainHeaderThirdContent {
            font: normal normal 600 38px/45px Poppins;
        }
        .bodyTextThirdContent {
            top: 180px;
        }
        .actionButtonThirdContent {
            top: 245px;
        }
    }
</style>