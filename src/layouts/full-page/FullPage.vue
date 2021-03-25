<template>
  <div class="layout--full-page">
    <div class="flex w-full vx-row no-gutter justify-center items-center" style="background: #fff !important; height: 90px;" v-if="scowComp === 1">
      <div style="width: 100%;">
        <vs-navbar class="p-5">
          <div slot="title">
            <vs-navbar-title>
              <img src="@/assets/images/newUpLeadLogo.png" alt="content-img" class="responsive" style="width: 50%; cursor: pointer;" @click="handleRedirectToView('/pages/home')">
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
                    <vs-list-item class="list-item" v-for="listItem in list" :key="listItem.socialMedia">
                      <vs-avatar :src="listItem.logo"/>
                      <span class="spanTagInCustomDropDown">{{listItem.socialMedia}}</span>
                    </vs-list-item>
                  </transition-group>
                </vs-list>
              </vs-dropdown-menu>
            </vs-dropdown>
            <!-- <a id="firstTabIndex" v-on:mouseover="handleOver()" v-on:mouseout="removeHandleOver()" href="#">
              Products
              <feather-icon icon="ChevronDownIcon" svgClasses="h-4 w-4 ml-1" />
            </a> -->
          </vs-navbar-item>
          <vs-navbar-item index="1">
            <a href="/pages/pricing">Pricing</a>
          </vs-navbar-item>
          <vs-navbar-item index="2">
            <a href="/">Our Data</a>
          </vs-navbar-item>
          <vs-navbar-item index="3">
            <a href="/">Reviews</a>
          </vs-navbar-item>
          <vs-navbar-item index="4">
            <a href="/">About Us</a>
          </vs-navbar-item>
          <vs-navbar-item index="5" class="loginContent">
            <vs-button color="dark" type="flat" icon-pack="feather" icon="icon-user">Login</vs-button>
            <a href="/" class="headerLogin">Login</a>
          </vs-navbar-item>
          <vs-navbar-item index="6">
            <vs-button class="startFreeTrial" color="primary" type="filled">Start Free Trial</vs-button>
            <a href="/" class="headerLogin">Start Free Trial</a>
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
          socialMedia: "Prospector",
          logo: "https://mcusercontent.com/28bc087ca1b79740b9ea0d695/images/6972ee2b-e515-4300-a8e9-b2c6a947aa77.png",
        },
        {
          socialMedia: "Data Enrichment",
          logo: "https://mcusercontent.com/28bc087ca1b79740b9ea0d695/images/21c178c5-83db-48b8-937a-a65d633a278c.png",
        },
        {
          socialMedia: "Chrome Extension",
          logo: "https://mcusercontent.com/28bc087ca1b79740b9ea0d695/images/7925cfc6-d696-4718-82c8-88a93cf822fa.png",
        },
        {
          socialMedia: "API",
          logo: "https://mcusercontent.com/28bc087ca1b79740b9ea0d695/images/eb39716f-f92d-417b-b831-b33c1e64724a.png",
        },
        {
          socialMedia: "Email Verification",
          logo: "https://mcusercontent.com/28bc087ca1b79740b9ea0d695/images/1d79bd34-5e28-495c-bbf4-8e3360729059.png",
        },
        {
          socialMedia: "Technographics",
          logo: "https://mcusercontent.com/28bc087ca1b79740b9ea0d695/images/bb2e22ef-c156-4da3-b896-ce55130814d6.png",
        },
        {
          socialMedia: "Email Finder",
          logo: "https://mcusercontent.com/28bc087ca1b79740b9ea0d695/images/d2128fe1-fd24-4cbb-ad7f-75fda4fa6a06.png",
        }
      ],
      scowComp: 0
    };
  },
  created() {
    this.handleHeaderComponent();
  },
  methods: {
    handleHeaderComponent() {
      if (this._routerRoot._route.path === "/pages/home" || this._routerRoot._route.path === "/pages/pricing") {
        this.scowComp = 1;
      } else {
        this.scowComp = 0;
      }
    },
    handleRedirectToView(path) {
      this.$router.push(path);
    },
    handleOver() {
      document.getElementById("vsDropdown").click();
    },
    removeHandleOver() {
      document.getElementById("vsDropdown").onreset();
    }
  }
})
</script>


<style>
  .vs-con-items {
    margin-right: auto;
    margin-left: 6%;
  }
  .spanTagInCustomDropDown {
    padding-left: 5px;
    font-weight: 500;
    bottom: 10px;
    position: relative;
    cursor: pointer;
  }
  .spanTagInCustomDropDown:hover {
    font-weight: 600;
  }
  .vs-navbar--title {
    display: flex;
    justify-content: flex-end;
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
    font-size: 18px;
  }
  .anqurTagAsBtn {
    color: inherit;
    font-family: "Gilroy",Sans-serif;
    font-size: 17px;
    font-weight: 500;
    color: #69727A;
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
    color: #69727A;
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