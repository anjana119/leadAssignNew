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
            <vs-button class="startFreeTrial" color="dark" type="filled">
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
          logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/452848e7-a01b-4a36-8f4f-5394e9bd7f60.png",
        },
        {
          text: "Data Enrichment",
          logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/9bb655cf-d7bb-41c8-b356-da6b57936da6.png",
        },
        {
          text: "Chrome Extension",
          logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/b6ae1e21-1ff7-4e51-aacd-dc7d63b9f3fa.png",
        },
        {
          text: "API",
          logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/7a4ff23d-fd7f-419e-8c3e-428e997e16c1.png",
        },
        {
          text: "Email Verification",
          logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/c75b629d-fc9c-430a-8b02-3754bea7f606.png",
        },
        {
          text: "Technographics",
          logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/850a7c21-e77b-41f4-9d46-736aeacc78ee.png",
        },
        {
          text: "Email Finder",
          logo: "https://mcusercontent.com/122a616be556c3f722865e0cf/images/8b0a0a78-ede2-41c3-b91b-6b96ddb316d3.png",
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
    background: #142537 !important;
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
  @media only screen and (max-width: 1440px) {
    .vs-navbar--title {
      padding-left: 105px;
    }
  }
  @media only screen and (max-width: 1280px) {
    .vs-navbar--title {
      justify-content: end;
      padding-left: 0px;
      margin-left: -35px;
    }
    .vs-con-items {
      margin-left: 0%;
    }
    .vs-navbar--header {
      padding-left: 0px;
    }
  }
  @media only screen and (max-width: 1024px) {
    .vs-navbar--title {
      margin-left: -4px;
    }
    .vs-con-items {
      margin-left: -28%;
    }
  }
  @media only screen and (max-width: 800px) {
    .vs-navbar--title {
      display: none;
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