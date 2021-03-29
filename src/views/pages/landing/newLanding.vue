<template>
    <div class="layout--full-page">
        <div
            class="flex w-full vx-row no-gutter justify-center items-center"
            style="background-image: linear-gradient(to left, #6359ef, #3a338b); height: 90px;"
        >
            <div style="width: 100%;">
                <vs-navbar class="p-5">
                    <div slot="title">
                        <vs-navbar-title>
                            <!-- <img
                                src="@/assets/images/newUpLeadLogo.png"
                                alt="content-img"
                                class="responsive"
                                style="width: 50%; cursor: pointer;"
                                @click="handleRedirectToView('/pages/home')"
                            /> -->
                            <span @click="handleRedirectToView('/pages/home')" style="font-size: 45px; color: white; font-weight: 200; curser: pointer !important;">
                                O2O
                                <span style="font-weight: 600; margin-left: -12px;">
                                    LEADS
                                </span>
                            </span>
                        </vs-navbar-title>
                    </div>
                    <vs-navbar-item index="0">
                        <vs-dropdown vs-custom-content vs-trigger-click id="vsDropdown">
                            <a class="flex items-center anqurTagAsBtn" href.prevent>
                                <span style="curser: pointer;">Products</span>
                                <feather-icon icon="ChevronDownIcon" svgClasses="h-4 w-4 ml-1" />
                            </a>
                            <vs-dropdown-menu class="dropdown-login">
                                <vs-list>
                                    <transition-group>
                                        <vs-list-item class="list-item" v-for="listItem in list" :key="listItem.text">
                                            <vs-avatar :src="listItem.logo"/>
                                            <span class="spanTagInCustomDropDown" @click="handleSelectDropdownValue(listItem.text)">
                                                {{listItem.text}}
                                            </span>
                                        </vs-list-item>
                                    </transition-group>
                                </vs-list>
                            </vs-dropdown-menu>
                        </vs-dropdown>
                    </vs-navbar-item>
                    <vs-navbar-item index="1">
                        <a
                            style="cursor: pointer;"
                            :class="path === 'pricing' ? 'selectedTabSection' : ''"
                            @click="handleRedirectToView('/pages/home')"
                        >
                            Pricing
                        </a>
                    </vs-navbar-item>
                    <vs-navbar-item index="2">
                        <a
                            style="cursor: pointer;"
                            :class="path === 'ourData' ? 'selectedTabSection' : ''"
                            @click="handleRedirectToView('/pages/home')"
                        >
                            Our Data
                        </a>
                    </vs-navbar-item>
                    <vs-navbar-item index="3">
                        <a
                            style="cursor: pointer;"
                            :class="path === 'review' ? 'selectedTabSection' : ''"
                            @click="handleRedirectToView('/pages/home')"
                        >
                            Reviews
                        </a>
                    </vs-navbar-item>
                    <vs-navbar-item index="4">
                        <a
                            style="cursor: pointer;"
                            :class="path === 'about-us' ? 'selectedTabSection' : ''"
                            @click="handleRedirectToView('/pages/home')"
                        >
                            About Us
                        </a>
                    </vs-navbar-item>
                    <vs-navbar-item index="5">
                        <vs-button
                            color="dark"
                            type="flat"
                            icon-pack="feather"
                            icon="icon-user"
                            @click="handleRedirectToView('/pages/home')"
                        >
                            Login
                        </vs-button>
                        <a
                            style="cursor: pointer;"
                            class="headerLogin"
                            :class="path === 'review' ? 'selectedTabSection' : ''"
                            @click="handleRedirectToView('/pages/home')"
                        >
                            Login
                        </a>
                    </vs-navbar-item>
                    <vs-navbar-item index="6">
                        <vs-button class="startFreeTrial" color="danger" type="filled">Start Free Trial</vs-button>
                        <a style="cursor: pointer;" href="/" class="headerLogin">Start Free Trial</a>
                    </vs-navbar-item>
                </vs-navbar>
            </div>
        </div>
        <div style="background-image: linear-gradient(to left, #6359ef, #3a338b); height: auto !important;">
            <div class="vx-row">
                <div class="vx-col w-full sm:w-1/2 md:w-1/2 landingBodyFirstCol" style="padding-top: 100px; padding-left: 175px;">
                    <div style="max-width: 60%;">
                        <h1 class="mainHeaderContent">
                            Import & Export Prospecting Leads.
                        </h1>
                    </div>
                    <div class="bodyTextContentDiv">
                        <span class="bodyTextContent">
                            Build prospecting lists free from dodgy data, bad-fit buyers and low-qualified leads.
                        </span>
                    </div>
                    <div style="max-width: 80%;">
                        <vs-input size="large" class="inputx emailField" placeholder="" />
                        <vs-button color="danger" type="filled" class="emailFieldBtn">Grab 5 Free Leads Now</vs-button>
                    </div>
                </div>
                <div class="vx-col w-full sm:w-1/2 md:w-1/2" style="padding-top: 50px; display: flex; justify-content: center;">
                    <img src="https://mcusercontent.com/5f6eb72b3f7a35a73b7c7e747/images/37b34b24-5fae-436b-9134-e3cc8bcfeb69.png" alt="content-img" style="height: 500px; width: 550px; position: relative; top: 27px;">
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default ({
  data() {
    return {
      list: [
        {
          text: "Prospector",
          logo: "https://mcusercontent.com/28bc087ca1b79740b9ea0d695/images/d0571644-4fe5-4d7d-96cb-e347f250eb40.png",
        },
        {
          text: "Data Enrichment",
          logo: "https://mcusercontent.com/28bc087ca1b79740b9ea0d695/images/c5b4e495-3cb1-49f4-a2ba-d79ff7a0b9e1.png",
        },
        {
          text: "Chrome Extension",
          logo: "https://mcusercontent.com/28bc087ca1b79740b9ea0d695/images/be0b6b98-94db-4925-bd33-fffb3a9ffe69.png",
        },
        {
          text: "API",
          logo: "https://mcusercontent.com/28bc087ca1b79740b9ea0d695/images/6d9f895f-dfda-4919-9813-7ca6b285a973.png",
        },
        {
          text: "Email Verification",
          logo: "https://mcusercontent.com/28bc087ca1b79740b9ea0d695/images/eb5d64d7-eeeb-4581-b26c-7b6540b56714.png",
        },
        {
          text: "Technographics",
          logo: "https://mcusercontent.com/28bc087ca1b79740b9ea0d695/images/6a7308aa-1d3e-4b78-86fc-ce7424929c00.png",
        },
        {
          text: "Email Finder",
          logo: "https://mcusercontent.com/28bc087ca1b79740b9ea0d695/images/11455135-03e3-4be7-bc53-49f1a7880a71.png",
        }
      ],
      path: "",
      scowComp: 0
    };
  },
  watch: {
    "$route"() {
      this.path = this._routerRoot._route.path === "/pages/home"  ? '' :
        this._routerRoot._route.path === "/pages/pricing" ? "pricing" :
        this._routerRoot._route.path === "/pages/ourData" ? "ourData" :
        this._routerRoot._route.path === "/pages/review" ? "review" :
        "about-us";
    }
  },
  created() {
    this.handleRouteMode();
  },
  methods: {
    handleSelectDropdownValue(value) {
        alert(value);
    },
    handleRouteMode() {
      this.path = this._routerRoot._route.path === "/pages/home"  ? '' :
        this._routerRoot._route.path === "/pages/pricing" ? "pricing" :
        this._routerRoot._route.path === "/pages/ourData" ? "ourData" :
        this._routerRoot._route.path === "/pages/review" ? "review" :
        "about-us";
    },
    handleRedirectToView(path) { 
        this.$router.push(path);
    }
  }
})
</script>

<style>
    .vs-con-items {
        margin: 0px;
    }
    [dir] .vs-input--input.large {
        border: none !important;
        box-shadow: none !important;
        width: 65%;
    }
    .emailField {
        background-color: rgb(255, 255, 255);
        border-color: rgb(222, 232, 235);
        border-width: 1px;
        border-radius: 5px;
        height: 50px;
        font-size: 18px;
        min-height: 59px;
        padding: 7px 20px;
        width: 100%;
        max-width: 100%;
        border: 1px solid #e2e2e2;
    }
    .emailFieldBtn {
        position: relative;
        bottom: 59px;
        float: right;
        right: 0px;
        border-radius: 0px 5px 5px 0px;
        padding-bottom: 20px !important;
        padding-top: 21px !important;
    }
    .bodyTextContentDiv {
        margin-top: 25px;
        margin-bottom: 30px;
        max-width: 63%;
    }
    .bodyTextContent {
        color: white;
        font-weight: 500;
    }
    .anquerTag {
        text-decoration: underline;
        cursor: pointer;
    }
    .anquerTag:hover {
        font-size: 15px;
    }
    .mainHeaderContent {
        font-size: 55px;
        font-weight: 600;
        color: white;
        font-family: sans-serif;
    }
    .vs-navbar {
        background: transparent !important;
    }
    .spanTagInCustomDropDown {
        padding-left: 5px;
        font-weight: 500;
        bottom: 10px;
        position: relative;
        cursor: pointer;
    }
    .selectedTabSection {
        font-size: 17px !important;
        font-weight: 600 !important;
    }
    .spanTagInCustomDropDown:hover {
        font-weight: 600;
    }
    .vs-navbar--title {
        display: flex;
        justify-content: flex-start;
    }
    .vs-list {
        padding: 8px;
    }
    .vs-list--slot {
        margin-left: 0px !important;
        margin-bottom: -6px;
    }
    .headerLogin {
        display: none !important;
    }
    .vs-list--item {
        padding: 5px;
    }
    .con-vs-avatar {
        margin: 0px;
    }
    .vs-navbar .vs-navbar--item a {
        color: inherit;
        font-family: "Gilroy",Sans-serif;
        font-size: 17px;
        font-weight: 500;
        color: white;
        padding: 15px 12px 15px 12px;
    }
    .vs-navbar-color-transparent .vs-navbar--item a:hover {
        color: white !important;
        font-size: 18px;
    }
    .anqurTagAsBtn {
        color: inherit;
        font-family: "Gilroy",Sans-serif;
        font-size: 17px;
        font-weight: 500;
        color: white;
        padding: 15px 12px 15px 12px;
    }
    .vs-popup--header {
        display: none;
    }
    .vs-con-dropdown {
        cursor: pointer;
    }
    .vs-navbar .vs-navbar--item a:hover {
        font-size: 18px;
    }
    .vs-button-dark.vs-button-border:hover, .vs-button-dark.vs-button-flat:hover {
        background: transparent !important;
        font-size: 18px;
    }
    .vs-button-dark.vs-button-border:hover, .vs-button-dark.vs-button-flat {
        background: transparent !important;
        color: inherit;
        font-family: "Gilroy",Sans-serif;
        font-size: 17px;
        font-weight: 500;
        color: white;
        padding: 15px 12px 15px 12px;
    }
    @media only screen and (max-width: 1280px) {
        .vs-navbar--title {
            justify-content: center;
        }
        .vs-con-items {
            margin-left: 0%;
        }
    }
    @media only screen and (max-width: 1024px) {
        .vs-navbar--title {
            justify-content: flex-start;
        }
        .vs-con-items {
            margin-left: -28%;
        }
    }
    @media only screen and (max-width: 800px) {
        .vs-navbar--title {
            justify-content: flex-start;
        }
        .vs-    con-items {
            margin-left: 0%;
        }
        .headerLogin {
            display: block !important;
        }
        .vs-button-dark.vs-button-border:hover, .vs-button-dark.vs-button-flat {
            display: none !important;
        }
        .startFreeTrial {
            display: none;
        }
  }
</style>