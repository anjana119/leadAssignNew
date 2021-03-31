<template>
    <div style="background: white !important; height: auto !important;">
        <div class="flex w-full no-gutter justify-center" style="background: rgb(251 251 255); padding-bottom: 100px;">
            <div style="padding-top: 80px;">
                <h1 class="headingSecondOurData">
                    Why Choose O2OLeads?
                </h1>
                <div class="vx-row" style="display: flex; justify-content: center; margin-bottom: 35px;">
                    <div class="vx-col w-full sm:w-1/1 md:w-1/3 lg:w-1/3 secondColOurData" v-for="(card, index) in cardList" :key="index">
                        <div class="ourDataBlogContent">
                            <div class="flex justify-center flex items-center text-center p-6">
                                <div>
                                    <vs-avatar size="70px" :src="card.logo"/>
                                    <h3 class="mb-4 font-bold cardHeaderOurDataSecond">
                                        {{ card.heding }}
                                    </h3>
                                    <span class="cardTextOurData">
                                        {{ card.text }}
                                    </span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                cardList: [
                    {
                        logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/319d8497-be79-4eec-a7d9-28f4a50c0bce.png",
                        text: "O2Oleads gives you access to 54M+ business contacts worldwide, making it easy for you to build targeted prospect lists. To identify your ideal prospects, search by title, job function, management level, industry, location, company size, technologies used and more.",
                        heding: "54M+ B2B Contacts At Your Fingertips"
                    },
                    {
                        logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/effdac34-1812-40d3-8ccb-b0ef7695a71e.png",
                        text: "O2Oleads is the only tool in the market to provide real-time email verification. Anytime you download or export leads, we verify the email address in real-time. This translates into higher response rates and more conversions for you.",
                        heding: "High Quality Real-Time Verified Data"
                    },
                    {
                        logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/83b3edb1-7c44-4746-ad03-363c28c5948c.png",
                        text: "O2Oleads automatically enriches your data with over 50 different data points, including job function, management level, social media links, and more. This gives you more context, and allows you to build rapport with your prospects.",
                        heding: "Data Enrichment with 50+ Data Points"
                    }
                ]
            };
        }
    }
</script>

<style>
.mainRow {
    padding: 0px;
}
.secondColOurData {
    display: flex;
    justify-content: center;
    padding-top: 100px;
    padding-bottom: 25px;
    max-width: 22%
}
.ourDataBlogContent {
    border-radius: 16px 16px 16px 16px;
    border-style: solid;
    border-width: 1px 1px 1px 1px;
    border-color: #DEE8EB;
    transition: background 0.3s,border 0.3s,border-radius 0.3s,box-shadow 0.3s;
    margin: 0 12px 0 12px;
    padding: 31px 22px 31px 22px;
    max-width: 100%;
    box-shadow: 0px 0px 8px 0px rgb(0 0 0 / 10%);
}
.headingFirstOurData {
    color: #091D30;
    font-family: "Gilroy",Sans-serif;
    font-size: 50px;
    font-weight: 700;
    line-height: 70px;
    width: 50%;
    word-wrap: break-word;
    text-align: center;
    margin-left: auto;
    margin-right: auto;
}
.headingSecondOurData {
    color: #091D30;
    font-family: "Gilroy",Sans-serif;
    line-height: 70px;
    font-size: 40px;
    font-weight: 600;
    word-wrap: break-word;
    text-align: center;
    margin-left: auto;
    margin-right: auto;
    width: 100%;
    margin-bottom: 60px;
}
.cardInOurData {
    border-style: solid;
    border-width: 1px 1px 1px 1px;
    border-color: #e4e4e4;
    box-shadow: 0px 0px 8px 0px rgb(0 0 0 / 10%);
    transition: background 0.3s,border 0.3s,border-radius 0.3s,box-shadow 0.3s;
    margin: 50px 12px 0 0px;
    padding: 25px 0px 25px 0px;
    height: 210px;
}
.cardHeaderOurData {
    color: rgba(var(--vs-primary),1);
    font-family: "Gilroy",Sans-serif;
    font-size: 50px;
    line-height: 54px;
}
.cardHeaderOurDataSecond {
    font-size: 24px;
    font-weight: 800;
    color: #091D30;
    font-family: var(--e-global-typography-primary-font-family),Sans-serif;
}
.cardTextOurData {
    color: var(--e-global-color-58870b7e);
    font-family: "Gilroy",Sans-serif;
    font-size: 16px;
    font-weight: 500;
    line-height: 24px;
}
@media only screen and (max-width: 800px) {
    .headingFirstOurData {
        width: 100%;
        font-size: 40px;
    }
    .headingSecondOurData {
        width: 100%;
        font-size: 30px;
    }
    .mainRow {
        padding: 0px 20px 0px 20px;
    }
    .secondColOurData {
        max-width: 75%;
        margin-bottom: 20px;
    }
}
</style>