<template>
    <div style="background: white !important; height: auto !important;">
        <div class="flex w-full no-gutter justify-center" style="margin-bottom: 100px;">
            <div style="padding-top: 80px;">
                <h1 class="headingFirstOurData">
                    Get Access To The Highest Quality Data
                </h1>
                <div>
                    <div class="vx-row mainRow">
                        <div class="vx-col w-1/2 md:w-1/4 xl:w-1/4" v-for="(card, index) in cardList" :key="index">
                            <vx-card class="overflow-hidden cardInOurData" style="cursor: pointer;">
                                <div slot="no-body">
                                    <div class="flex justify-center flex items-center text-center p-6" >
                                        <div>
                                            <h2 class="mb-1 font-bold cardHeaderOurData">
                                                {{ card.heding }}
                                            </h2>
                                            <span class="cardTextOurData">
                                                {{ card.text }}
                                            </span>
                                        </div>
                                    </div>
                                </div>
                            </vx-card>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="flex w-full no-gutter justify-center" style="background: rgb(251 251 255); padding-bottom: 100px;">
            <div style="padding-top: 80px;">
                <h1 class="headingSecondOurData">
                    O2OLeads Data Collection and Verification Process
                </h1>
                <div
                    class="vx-row"
                    style="display: flex; justify-content: center; margin-bottom: 35px;"
                    v-for="(item, mainIndex) in secondCardList"
                    :key="mainIndex"
                >
                    <div
                        class="vx-col w-1/2 md:w-1/4 lg:w-1/4 secondColOurData"
                        v-for="(card, index) in item.col"
                        :key="index"
                    >
                        <div class="ourDataBlogContent">
                            <div class="flex justify-center flex items-center text-center p-6">
                                <div>
                                    <vs-avatar size="70px" :src="card.logo"/>
                                    <h2 class="mb-3 font-bold cardHeaderOurDataSecond">
                                        {{ card.heding }}
                                    </h2>
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
                        text: "B2B Contacts with Email Addresses",
                        heding: "+54M"
                    },
                    {
                        text: "Global Company Profiles",
                        heding: "+14M"
                    },
                    {
                        text: "Technologies Tracked",
                        heding: "+16K"
                    },
                    {
                        text: "Accuracy Guarantee",
                        heding: "95%"
                    }
                ],
                secondCardList: [
                    {
                        col: [
                            {
                                logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/91ea2ff6-ffd5-46ba-b54b-41e1fdc81a29.png",
                                text: "We search and analyze millions of public documents to hunt down relevant information",
                                heding: "STEP 1"
                            },
                            {
                                logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/3882221e-644c-4331-9607-58fe39f640a0.png",
                                text: "To supplement our data, and make it even more comprehensive, we also license data from trusted third parties",
                                heding: "STEP 2"
                            },
                            {
                                logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/2e256e7e-c606-4adc-a499-36f12aa882c3.png",
                                text: "We analyze, categorize and label our data (Machine Learning, Rule-Based Learning, Proprietary Algorithms)",
                                heding: "STEP 3"
                            },
                            {
                                logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/9249c942-d8c7-4432-ae8a-4eb711a16954.png",
                                text: "We test and validate our information to remove incorrect, stale and unverifiable information",
                                heding: "STEP 4"
                            }
                        ]
                    },
                    {
                        col: [
                            {
                                logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/d988abaa-8849-4545-9d57-180eefb126a7.png",
                                text: "Accurate information is loaded into the UpLead database, ready for customers to access (By API or Web Application)",
                                heding: "STEP 5"
                            },
                            {
                                logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/94022abb-147f-4039-846a-201f0a535519.png",
                                text: "At the point where customers download their data, we perform real-time email verification, and put our data through a final round of tests",
                                heding: "STEP 6"
                            },
                            {
                                logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/cd380fef-c29f-4d2c-8849-6b5d1fff0cd3.png",
                                text: "We deliver our accurate data to our customers (Any emails that could not be verified gets sent back to our team of manual researchers.)",
                                heding: "STEP 7"
                            },
                            {
                                logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/ab27e78b-4c49-4483-87d6-f2c12bc3c602.png",
                                text: "Researchers comb through the data painstakingly, and update UpLead’s database to close the loop",
                                heding: "STEP 8"
                            }
                        ]
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
    max-width: 18%
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
    width: 40%;
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
.cardInOurData:hover {
    border-width: 2px 2px 2px 2px;
}
.cardInOurDataSecond {
    border-style: solid;
    border-width: 1px 1px 1px 1px;
    border-color: #e4e4e4;
    box-shadow: 0px 0px 8px 0px rgb(0 0 0 / 10%);
    transition: background 0.3s,border 0.3s,border-radius 0.3s,box-shadow 0.3s;
    margin: 50px 12px 0 0px;
    padding: 25px 0px 25px 0px;
}
.cardHeaderOurData {
    color: #fb4141;
    font-family: "Gilroy",Sans-serif;
    font-size: 50px;
    line-height: 54px;
}
.cardHeaderOurDataSecond {
    font-family: "Gilroy",Sans-serif;
    font-size: 25px;
    text-transform: uppercase;
    line-height: 32px;
    letter-spacing: 1.8px;
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
        max-width: 100%;
        margin-bottom: 20px;
    }
}
</style>