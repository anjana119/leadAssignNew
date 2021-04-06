<template>
    <div style="background: white !important; height: auto !important;">
        <div class="flex w-full no-gutter justify-center" style="margin-bottom: 100px;">
            <div style="padding-top: 80px;">
                <h1 class="headingFirstOurData">
                    Get Access To The Highest Quality Data
                </h1>
                <div>
                    <div class="vx-row mainRow">
                        <div class="vx-col w-1/2 md:w-1/4 xl:w-1/4 analyticCardBox">
                            <vx-card class="overflow-hidden cardInOurData" style="cursor: pointer;">
                                <div slot="no-body">
                                    <div class="flex justify-center flex items-center text-center p-6" >
                                        <div>
                                            <h2 id="Count1" class="mb-1 font-bold cardHeaderOurData">
                                                +54M
                                            </h2>
                                            <span class="cardTextOurData">
                                                B2B Contacts with Email Addresses
                                            </span>
                                        </div>
                                    </div>
                                </div>
                            </vx-card>
                        </div>
                        <div class="vx-col w-1/2 md:w-1/4 xl:w-1/4 analyticCardBox">
                            <vx-card class="overflow-hidden cardInOurData" style="cursor: pointer;">
                                <div slot="no-body">
                                    <div class="flex justify-center flex items-center text-center p-6" >
                                        <div>
                                            <h2 id="Count2" class="mb-1 font-bold cardHeaderOurData">
                                                +14M
                                            </h2>
                                            <span class="cardTextOurData">
                                                Global Company Profiles
                                            </span>
                                        </div>
                                    </div>
                                </div>
                            </vx-card>
                        </div>
                        <div class="vx-col w-1/2 md:w-1/4 xl:w-1/4 analyticCardBox">
                            <vx-card class="overflow-hidden cardInOurData" style="cursor: pointer;">
                                <div slot="no-body">
                                    <div class="flex justify-center flex items-center text-center p-6" >
                                        <div>
                                            <h2 id="Count3" class="mb-1 font-bold cardHeaderOurData">
                                                +16K
                                            </h2>
                                            <span class="cardTextOurData">
                                                Technologies Tracked
                                            </span>
                                        </div>
                                    </div>
                                </div>
                            </vx-card>
                        </div>
                        <div class="vx-col w-1/2 md:w-1/4 xl:w-1/4 analyticCardBox">
                            <vx-card class="overflow-hidden cardInOurData" style="cursor: pointer;">
                                <div slot="no-body">
                                    <div class="flex justify-center flex items-center text-center p-6" >
                                        <div>
                                            <h2 id="Count4" class="mb-1 font-bold cardHeaderOurData">
                                                95%
                                            </h2>
                                            <span class="cardTextOurData">
                                                Accuracy Guarantee
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
                    v-for="(item, mainIndex) in secondCardList"
                    :key="mainIndex"
                >
                    <div
                        class="vx-col w-full sm:w-1/2 md:w-1/4 lg:w-1/4 secondColOurData"
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
                secondCardList: [
                    {
                        col: [
                            {
                                logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/f38a3782-e115-49bd-80c0-198585449437.png",
                                text: "We search and analyze millions of public documents to hunt down relevant information",
                                heding: "STEP 1"
                            },
                            {
                                logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/da0f8ee1-1192-411c-ad0c-5e5d9f8ab384.png",
                                text: "To supplement our data, and make it even more comprehensive, we also license data from trusted third parties",
                                heding: "STEP 2"
                            },
                            {
                                logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/23b8d111-533a-4ac8-9bba-438d05b30fd5.png",
                                text: "We analyze, categorize and label our data (Machine Learning, Rule-Based Learning, Proprietary Algorithms)",
                                heding: "STEP 3"
                            },
                            {
                                logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/126725a5-29d4-445f-b01a-2db83c0b82db.png",
                                text: "We test and validate our information to remove incorrect, stale and unverifiable information",
                                heding: "STEP 4"
                            }
                        ]
                    },
                    {
                        col: [
                            {
                                logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/10e035f0-0194-4e62-a09a-9d156e83122e.png",
                                text: "Accurate information is loaded into the UpLead database, ready for customers to access (By API or Web Application)",
                                heding: "STEP 5"
                            },
                            {
                                logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/9c00ad6b-9e3c-4be2-817d-05574e90542f.png",
                                text: "At the point where customers download their data, we perform real-time email verification, and put our data through a final round of tests",
                                heding: "STEP 6"
                            },
                            {
                                logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/87e21b8c-19db-49e0-aa77-e827e0229bf9.png",
                                text: "We deliver our accurate data to our customers (Any emails that could not be verified gets sent back to our team of manual researchers.)",
                                heding: "STEP 7"
                            },
                            {
                                logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/5f3ecc61-320a-466d-b898-0bb469c8c3f4.png",
                                text: "Researchers comb through the data painstakingly, and update UpLead’s database to close the loop",
                                heding: "STEP 8"
                            }
                        ]
                    }
                ]
            };
        },
        watch: {},
        mounted() {
            this.animateValue();
            this.animateValue2();
            this.animateValue3();
            this.animateValue4();
        },
        created() {
            this.animateValue();
            this.animateValue2();
            this.animateValue3();
            this.animateValue4();
        },
        methods: {
            animateValue(start = 0, end = null, duration = 3000) {
                let obj = document.getElementById('Count1');
                if (obj) {
                    // save starting text for later (and as a fallback text if JS not running and/or google)
                    var textStarting = obj.innerHTML;
                    // remove non-numeric from starting text if not specified
                    end = end || parseInt(textStarting.replace(/\D/g, ""));
                    var range = end - start;
                    // no timer shorter than 50ms (not really visible any way)
                    var minTimer = 50;
                    // calc step time to show all interediate values
                    var stepTime = Math.abs(Math.floor(duration / range));
                    // never go below minTimer
                    stepTime = Math.max(stepTime, minTimer);
                    // get current time and calculate desired end time
                    var startTime = new Date().getTime();
                    var endTime = startTime + duration;
                    var timer;
                    function run() {
                        var now = new Date().getTime();
                        var remaining = Math.max((endTime - now) / duration, 0);
                        var value = Math.round(end - (remaining * range));
                        // replace numeric digits only in the original string
                        obj.innerHTML = textStarting.replace(/([0-9]+)/g, value);
                        if (value == end) {
                            clearInterval(timer);
                        }
                    }
                    timer = setInterval(run, stepTime);
                    run();
                }
            },
            animateValue2(start = 0, end = null, duration = 3000) {
                let obj = document.getElementById('Count2');
                if (obj) {
                    // save starting text for later (and as a fallback text if JS not running and/or google)
                    var textStarting = obj.innerHTML;
                    // remove non-numeric from starting text if not specified
                    end = end || parseInt(textStarting.replace(/\D/g, ""));
                    var range = end - start;
                    // no timer shorter than 50ms (not really visible any way)
                    var minTimer = 50;
                    // calc step time to show all interediate values
                    var stepTime = Math.abs(Math.floor(duration / range));
                    // never go below minTimer
                    stepTime = Math.max(stepTime, minTimer);
                    // get current time and calculate desired end time
                    var startTime = new Date().getTime();
                    var endTime = startTime + duration;
                    var timer;
                    function run() {
                        var now = new Date().getTime();
                        var remaining = Math.max((endTime - now) / duration, 0);
                        var value = Math.round(end - (remaining * range));
                        // replace numeric digits only in the original string
                        obj.innerHTML = textStarting.replace(/([0-9]+)/g, value);
                        if (value == end) {
                            clearInterval(timer);
                        }
                    }
                    timer = setInterval(run, stepTime);
                    run();
                }
            },
            animateValue3(start = 0, end = null, duration = 3000) {
                let obj = document.getElementById('Count3');
                if (obj) {
                    // save starting text for later (and as a fallback text if JS not running and/or google)
                    var textStarting = obj.innerHTML;
                    // remove non-numeric from starting text if not specified
                    end = end || parseInt(textStarting.replace(/\D/g, ""));
                    var range = end - start;
                    // no timer shorter than 50ms (not really visible any way)
                    var minTimer = 50;
                    // calc step time to show all interediate values
                    var stepTime = Math.abs(Math.floor(duration / range));
                    // never go below minTimer
                    stepTime = Math.max(stepTime, minTimer);
                    // get current time and calculate desired end time
                    var startTime = new Date().getTime();
                    var endTime = startTime + duration;
                    var timer;
                    function run() {
                        var now = new Date().getTime();
                        var remaining = Math.max((endTime - now) / duration, 0);
                        var value = Math.round(end - (remaining * range));
                        // replace numeric digits only in the original string
                        obj.innerHTML = textStarting.replace(/([0-9]+)/g, value);
                        if (value == end) {
                            clearInterval(timer);
                        }
                    }
                    timer = setInterval(run, stepTime);
                    run();
                }
            },
            animateValue4(start = 0, end = null, duration = 3000) {
                let obj = document.getElementById('Count4');
                if (obj) {
                    // save starting text for later (and as a fallback text if JS not running and/or google)
                    var textStarting = obj.innerHTML;
                    // remove non-numeric from starting text if not specified
                    end = end || parseInt(textStarting.replace(/\D/g, ""));
                    var range = end - start;
                    // no timer shorter than 50ms (not really visible any way)
                    var minTimer = 50;
                    // calc step time to show all interediate values
                    var stepTime = Math.abs(Math.floor(duration / range));
                    // never go below minTimer
                    stepTime = Math.max(stepTime, minTimer);
                    // get current time and calculate desired end time
                    var startTime = new Date().getTime();
                    var endTime = startTime + duration;
                    var timer;
                    function run() {
                        var now = new Date().getTime();
                        var remaining = Math.max((endTime - now) / duration, 0);
                        var value = Math.round(end - (remaining * range));
                        // replace numeric digits only in the original string
                        obj.innerHTML = textStarting.replace(/([0-9]+)/g, value);
                        if (value == end) {
                            clearInterval(timer);
                        }
                    }
                    timer = setInterval(run, stepTime);
                    run();
                }
            }
        }
    }
</script>

<style>
.mainRow {
    padding: 0px;
}
.vx-row {
    display: flex;
    justify-content: center;
    margin-bottom: 35px;
}
.secondColOurData {
    display: flex;
    justify-content: center;
    padding-top: 100px;
    padding-bottom: 25px;
    max-width: 18%;
    margin-bottom: 0px;
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
    color: #FF0000 !important;
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
}
@media (min-width: 250px) and (max-width: 1030px){
    .secondColOurData {
        width: 50% !important;
        max-width: 100%;
        margin-bottom: 30px;
    }
    .vx-row {
        padding-left: 25px;
        padding-right: 25px;
        margin-bottom: 0px;
    }
    .headingSecondOurData {
        width: 75%;
        line-height: 45px;
    }
    .analyticCardBox {
        width: 50% !important;
    }
}
</style>