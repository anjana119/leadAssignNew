<template>
  <div class="layout--full-page">
    <div
      class="flex w-full vx-row no-gutter justify-center items-center"
      style="background: #fff !important; height: auto;"
      v-if="scowComp === 1"
    >
      <div class="vx-col w-full" style="width: 100%;">
        <vs-navbar class="p-5">
          <div slot="title">
            <vs-navbar-title>
              <img
                src="@/assets/images/newUpLeadLogo.png"
                alt="content-img"
                class="responsive"
                style="width: 35%; height: 30px; cursor: pointer;"
                @click="handleRedirectToView('/pages/home')"
              />
            </vs-navbar-title>
          </div>
          <vs-navbar-item index="0">
            <vs-dropdown vs-custom-content vs-trigger-click id="vsDropdown">
              <a class="flex items-center anqurTagAsBtn" href.prevent>
                <span style="curser: pointer; font: normal normal medium 22px/33px Poppins;">
                  Products
                </span>
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
              style="cursor: pointer; font: normal normal medium 22px/33px Poppins;"
              :class="path === 'pricing' ? 'selectedTabSection' : ''"
              @click="handleRedirectToView('/pages/pricing')"
            >
              Pricing
            </a>
          </vs-navbar-item>
          <vs-navbar-item index="2">
            <a
              style="cursor: pointer; font: normal normal medium 22px/33px Poppins;"
              :class="path === 'ourData' ? 'selectedTabSection' : ''"
              @click="handleRedirectToView('/pages/ourData')"
            >
              Our Data
            </a>
          </vs-navbar-item>
          <vs-navbar-item index="3">
            <a
              style="cursor: pointer; font: normal normal medium 22px/33px Poppins;"
              :class="path === 'review' ? 'selectedTabSection' : ''"
              @click="handleRedirectToView('/pages/review')"
            >
              Reviews
            </a>
          </vs-navbar-item>
          <vs-navbar-item index="4">
            <a
              style="cursor: pointer; font: normal normal medium 22px/33px Poppins;"
              :class="path === 'about-us' ? 'selectedTabSection' : ''"
              @click="handleRedirectToView('/pages/about-us')"
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
              style="ffont: normal normal medium 22px/33px Poppins;"
              @click="handleRedirectToView('/pages/login')"
            >
              Login
            </vs-button>
            <a
              style="cursor: pointer; font: normal normal medium 22px/33px Poppins;"
              class="headerLogin"
              :class="path === 'review' ? 'selectedTabSection' : ''"
              @click="handleRedirectToView('/pages/login')"
            >
              Login
            </a>
          </vs-navbar-item>
          <vs-navbar-item index="6">
            <vs-button class="startFreeTrial" color="danger" type="filled">
              Start Free Trial
            </vs-button>
            <a style="cursor: pointer; font: normal normal medium 22px/33px Poppins;" href="/" class="headerLogin">
              Start Free Trial
            </a>
          </vs-navbar-item>
        </vs-navbar>
      </div>
    </div>
    <router-view></router-view>
  </div>
</template>

<script>
export default ({
  data() {
    return {
      list: [
        {
          text: "Prospector",
          logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/93a7c948-8386-4c53-8bed-5aa4bfe20f82.png",
        },
        {
          text: "Data Enrichment",
          logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/315a46c4-4fdd-45c7-b172-de776a3b2403.png",
        },
        {
          text: "Chrome Extension",
          logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/f33e5a69-3ad3-45db-85bf-335138af3609.png",
        },
        {
          text: "API",
          logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/a90dd4e0-ae61-42d5-9735-8adb64c650cc.png",
        },
        {
          text: "Email Verification",
          logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/c6a7ff87-f94e-4351-aa5a-9aef5cf841ac.png",
        },
        {
          text: "Technographics",
          logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/634a9c9f-bc62-4e23-9fd7-b8c9e5ed63cb.png",
        },
        {
          text: "Email Finder",
          logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/95e3a247-9edf-454a-a45d-c0d947b60737.png",
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
      this.handleHeaderComponent();
    }
  },
  created() {
    this.handleHeaderComponent();
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
    handleHeaderComponent() {
      if (
        this._routerRoot._route.path === "/pages/home" ||
        this._routerRoot._route.path === "/pages/pricing" ||
        this._routerRoot._route.path === "/pages/ourData" ||
        this._routerRoot._route.path === "/pages/review" ||
        this._routerRoot._route.path === "/pages/about-us"
      ) {
        this.scowComp = 1;
      } else {
        this.scowComp = 0;
      }
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
  .vs-navbar {
    background: white !important;
  }
  .spanTagInCustomDropDown {
    padding-left: 5px;
    bottom: 10px;
    position: relative;
    cursor: pointer;
    font: normal normal medium 22px/33px Poppins;
  }
  .spanTagInCustomDropDown:hover {
    font-weight: 600;
  }
  .selectedTabSection {
    font-size: 17px !important;
    font-weight: 600 !important;
  }
  .vs-navbar--title {
    display: flex;
    justify-content: flex-start;
    position: relative;
    padding-left: 76px;
  }
  .vs-list {
    padding: 15px;
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
  .loginContent {
    margin-left: 100px;
  }
  .vs-navbar .vs-navbar--item a {
    color: inherit;
    font-family: "Gilroy",Sans-serif;
    font-size: 17px;
    font-weight: 500;
    color: #69727A;
    padding: 15px 12px 15px 12px;
  }
  .vs-navbar-color-transparent .vs-navbar--item a:hover {
    color: #69727A !important;
  }
  .anqurTagAsBtn {
    color: inherit;
    font-family: "Gilroy",Sans-serif;
    font-size: 17px;
    font-weight: 500;
    color: white;
    padding: 15px 12px 15px 12px;
  }
  .vs-navbar--header {
    width: 38%;
    padding-left: 0px;
  }
  .vs-popup--header {
    display: none;
  }
  .vs-con-dropdown {
    cursor: pointer;
  }
  .startFreeTrial {
    background:#FF0000 !important;
    font-family: 'Poppins', sans-serif;
  }
  .vs-navbar .vs-navbar--item a:hover {
    font-weight: 600;
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
    color: #69727A;
    padding: 15px 12px 15px 12px;
  }
  @media only screen and (max-width: 1280px) {
    .vs-navbar--header {
      padding-left: 150px;
    }
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
    .vs-con-items {
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