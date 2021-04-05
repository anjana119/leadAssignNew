<template>
    <div style="background: white !important; height: auto !important;">
        <div class="flex w-full no-gutter justify-center">
            <div style="padding-top: 80px;">
                <h1 class="headingInPricing">
                    O2O Plans & Pricing
                </h1>
                <div style="text-align: center; margin-bottom: 40px;">
                    <span class="subHeader">
                        Find the plan that’s right for you.
                    </span>
                </div>
                <div style="text-align: center;">
                    <span class="inline-flex subHeaderOptions">
                        <span style="cursor: pointer;" @click="handleSwitch(false)">
                            Billed Monthly
                        </span>
                        <vs-switch color="danger" v-model="switch1" class="ml-8 mr-8" />
                        <span style="cursor: pointer;" @click="handleSwitch(true)">
                            Billed Annually -
                        </span>
                        <span class="ml-1 discount" @click="handleSwitch(true)">
                            Save 25%
                        </span>
                    </span>
                </div>
            </div>
        </div>
        <div style="display: flex; justify-content: center;" class="mb-5">
            <div class="vx-row" style="width: 67%;">
                <div class="vx-col w-full sm:w-1/2 md:w-1/4 lg:w-1/4 firstColPricing" style="padding-top: 70px; padding-bottom: 60px;">
                    <div class="pricingContentFree">
                        <h3 class="contentHeaderFree">
                            Free Trial
                        </h3>
                        <hr class="hrTag" />
                        <h1 class="priceCountFree">
                            $0
                        </h1>
                        <h5 class="creditLimitFree">
                            5 Credits
                        </h5>
                        <span class="testDriveFree">
                            Free Test Drive
                        </span>
                        <vs-button class="btnFreeContent" color="danger" type="filled">
                            Try For Free
                        </vs-button>
                        <hr class="hrTag" />
                        <vs-list style="color: white; margin-top: -15px; margin-left: -18px;">
                            <vs-list-item
                                v-for="(item, index) in freeItemListTextContent"
                                :key="index"
                                icon-pack="feather"
                                icon="icon-check-circle"
                                :title="item"
                            />
                        </vs-list>
                        <vs-button class="btnFreeContent" color="danger" type="filled">
                            Try For Free
                        </vs-button>
                    </div>
                </div>
                <div class="vx-col w-full sm:w-1/2 md:w-1/4 lg:w-1/4 secondColPricing" style="padding-top: 100px; padding-bottom: 25px;">
                    <div class="pricingContent">
                        <h3 class="contentHeader">
                            Essentials
                        </h3>
                        <hr class="hrTag" />
                        <h1 class="priceCount">
                            {{switch1 === true ? "$890" : "$99"}} 
                            <span style="font-size: 15px; color: #69727A; margin-left: -15px;">
                                {{switch1 === true ? "/year" : "/month"}}
                            </span>
                        </h1>
                        <h5 class="creditLimit">
                            <span style="color: #FF0000; font-weight: 500;">
                                {{switch1 === true ? "2,040" : "170"}} Credits
                            </span>
                            {{switch1 === true ? "Annually" : "Monthly"}}
                        </h5>
                        <span class="testDrive">Additional Credits
                            <span style="font-weight: 500!important; color: #091D30;">
                                $0.60
                            </span>
                        </span>
                        <vs-button class="btnContent" color="danger" type="filled">
                            Buy Now
                        </vs-button>
                        <hr class="hrTag" />
                        <vs-list class="anjana" style="color: #69727A; margin-top: -15px; margin-left: -18px;">
                            <vs-list-item
                                v-for="(item, index) in freeItemListTextContent"
                                :key="index"
                                icon-pack="feather"
                                icon="icon-check-circle"
                                :title="item"
                            />
                        </vs-list>
                        <vs-button class="btnContent" color="danger" type="filled">
                            Buy Now
                        </vs-button>
                    </div>
                </div>
                <div class="vx-col w-full sm:w-1/2 md:w-1/4 lg:w-1/4 thirdColPricing" style="padding-top: 100px; padding-bottom: 25px;">
                    <div class="pricingContent">
                        <h3 class="contentHeader">
                            Plus
                        </h3>
                        <hr class="hrTag" />
                        <h1 class="priceCount">
                            {{switch1 === true ? "$1790" : "$199"}} 
                            <span style="font-size: 15px; color: #69727A; margin-left: -15px;">
                                {{switch1 === true ? "/year" : "/month"}}
                            </span>
                        </h1>
                        <h5 class="creditLimit">
                            <span style="color: #FF0000; font-weight: 500;">
                                {{switch1 === true ? "4,800" : "400"}} Credits
                            </span>
                            {{switch1 === true ? "Annually" : "Monthly"}}
                        </h5>
                        <span class="testDrive">Additional Credits
                            <span style="font-weight: 500!important; color: #091D30;">
                                $0.50
                            </span>
                        </span>
                        <vs-button class="btnContent" color="danger" type="filled">
                            Buy Now
                        </vs-button>
                        <hr class="hrTag" />
                        <vs-list class="anjana" style="color: #69727A; margin-top: -15px; margin-left: -18px;">
                            <vs-list-item
                                v-for="(item, index) in freeItemListTextContent"
                                :key="index"
                                icon-pack="feather"
                                icon="icon-check-circle"
                                :title="item"
                            />
                        </vs-list>
                        <vs-button class="btnContent" color="danger" type="filled">
                            Buy Now
                        </vs-button>
                    </div>
                </div>
                <div class="vx-col w-full sm:w-1/2 md:w-1/4 lg:w-1/4 forthColPricing" style="padding-top: 100px; padding-bottom: 25px;">
                    <div class="pricingContent">
                        <h3 class="contentHeader">
                            Professional
                        </h3>
                        <hr class="hrTag" />
                        <h1 class="priceCount">
                            {{switch1 === true ? "$3590" : "$399"}} 
                            <span style="font-size: 15px; color: #69727A; margin-left: -15px;">
                                {{switch1 === true ? "/year" : "/month"}}
                            </span>
                        </h1>
                        <h5 class="creditLimit">
                            <span style="color: #FF0000; font-weight: 500;">
                                {{switch1 === true ? "12,000" : "1000"}} Credits
                            </span>
                            {{switch1 === true ? "Annually" : "Monthly"}}
                        </h5>
                        <span class="testDrive">
                            Additional Credits
                            <span style="font-weight: 500!important; color: #091D30;">
                                $0.40
                            </span>
                        </span>
                        <vs-button class="btnContent" color="danger" type="filled">
                            Buy Now
                        </vs-button>
                        <hr class="hrTag" />
                        <vs-list class="anjana" style="color: #69727A; margin-top: -15px; margin-left: -18px;">
                            <vs-list-item
                                v-for="(item, index) in freeItemListTextContent"
                                :key="index"
                                icon-pack="feather"
                                icon="icon-check-circle"
                                :title="item === 'Single User' ? 'Unlimited Users' : item"
                            />
                        </vs-list>
                        <vs-button class="btnContent" color="danger" type="filled">
                            Buy Now
                        </vs-button>
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
            switch1: false,
            freeItemListTextContent: [
                "Single User",
                "100% Verified Emails",
                "Unused Credits Rollover",
                "Data Enhancement",
                "Competitor Intelligence",
                "Technology Tracking",
                "Email Pattern Intel",
                "CRM Integration",
                "Chrome Extension",
                "No Contract"
            ]
        };
    },
    methods: {
        handleSwitch(value) {
            this.switch1 = value;
        }
    }
}
</script>

<style>
.headingInPricing {
    color: #091D30;
    font-family: "Gilroy",Sans-serif;
    font-size: 42px;
    font-weight: 700;
    line-height: 1.2;
    margin-bottom: 20px;
}
.subHeader {
    font-family: var(--e-global-typography-text-font-family),Sans-serif;
    color: #69727A;
    font-size: 20px;
    font-weight: 500;
}
.subHeaderOptions {
    font-family: var(--e-global-typography-text-font-family),Sans-serif;
    color: #69727A;
    font-size: 16px;
    font-weight: 200;
    line-height: 18px;
}
.btnFreeContent {
    background: white !important;
    color: #FF0000 !important;
    font-size: 15px;
    font-weight: 600;
    width: 100%;
    padding: 15px 0px 15px 0px;
    margin-top: 20px;
    margin-bottom: 10px;
}
.btnFreeContent:hover {
    background: #FF0000 !important;
    color: white !important;
    border: 1px solid white !important;
}
.btnContent {
    background: #FF0000 !important;
    color: white !important;
    font-size: 15px;
    font-weight: 600;
    width: 100%;
    padding: 15px 0px 15px 0px;
    margin-top: 20px;
    margin-bottom: 10px;
}
.btnContent:hover {
    background: white !important;
    color: #FF0000 !important;
    border: 1px solid #FF0000 !important;
}
.discount {
    color: #FF0000;
    font-weight: 600;
    cursor: pointer;
}
.hrTag {
    margin: 30px 0px 30px 0px;
    border-color: #eaeaea;
}
.priceCountFree {
    margin-bottom: -10px;
    color: #FFF;
    font-size: 50px;
    font-weight: 800;
    line-height: 58px;
}
.priceCount {
    margin-bottom: -10px;
    color: #091D30;
    font-size: 50px;
    font-weight: 500;
    line-height: 58px;
}
.pricingContent {
    border-radius: 16px 16px 16px 16px;
    border-style: solid;
    border-width: 1px 1px 1px 1px;
    border-color: #DEE8EB;
    transition: background 0.3s,border 0.3s,border-radius 0.3s,box-shadow 0.3s;
    margin: 0 12px 0 12px;
    padding: 31px 22px 31px 22px;
    width: 100%;
}
.pricingContentFree {
    background:#FF0000;
    border-radius: 16px 16px 16px 16px;
    border-style: solid;
    border-width: 1px 1px 1px 1px;
    border-color:#FF0000;
    transition: background 0.3s,border 0.3s,border-radius 0.3s,box-shadow 0.3s;
    margin: 0 12px 0 12px;
    padding: 31px 22px 31px 22px;
    width: 100%;
}
.vs-list--title {
    font-weight: 500;
}
.vs-list--item {
    border-bottom: none;
}
.creditLimitFree {
    color: #FFF;
    font-size: 20px;
    font-weight: 500;
    margin-top: 20px;
    line-height: 22px;
    margin-bottom: 5px;
}
.testDrive {
    color: #69727A;
    font-size: 16px;
    line-height: 24px;
}
.creditLimit {
    color: #69727A;
    font-size: 18px;
    font-weight: 200;
    line-height: 22px;
    margin-top: 22px;
    margin-bottom: 10px;
}
.testDriveFree {
    color: #FFF;
    font-size: 15px;
    font-weight: 500;
    line-height: 24px;
}
.contentHeader {
    color: #091D30;
    font-size: 24px;
    font-weight: 800;
}
.contentHeaderFree {
    color: #FFF;
    font-size: 24px;
    font-weight: 800;
}
.firstColPricing {
    display: flex;
    justify-content: flex-end;
}
.secondColPricing {
    display: flex;
    justify-content: center;
}
.thirdColPricing {
    display: flex;
    justify-content: center;
}
.forthColPricing {
    display: flex;
    justify-content: flex-start;
}
</style>