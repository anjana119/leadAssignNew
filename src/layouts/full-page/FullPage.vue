<template>
  <div class="layout--full-page">
    <div class="flex w-full vx-row no-gutter justify-center items-center" style="background: #fff !important; height: 90px;" v-if="scowComp === 1">
      <div style="width: 100%;">
        <vs-navbar v-model="activeItem" class="p-5">
          <div slot="title">
            <vs-navbar-title>
              <img src="@/assets/images/newUpLeadLogo.png" alt="content-img" class="responsive" style="width: 50%;">
            </vs-navbar-title>
          </div>
          <vs-navbar-item index="0">
            <vs-dropdown vs-custom-content vs-trigger-click>
              <a class="flex items-center anqurTagAsBtn" href.prevent>
                <span style="curser: pointer;">Products</span>
                <feather-icon icon="ChevronDownIcon" svgClasses="h-4 w-4 ml-1" />
              </a>
              <vs-dropdown-menu class="dropdown-login">
                  <vs-list>
                      <transition-group>
                          <vs-list-item class="list-item" v-for="listItem in list" :key="listItem.socialMedia" :title="listItem.socialMedia">
                            <vs-avatar src="https://i.imgur.com/ezM6SJ5.png"/>
                          </vs-list-item>
                      </transition-group>
                  </vs-list>
              </vs-dropdown-menu>
            </vs-dropdown>
          </vs-navbar-item>
          <vs-navbar-item index="0">
            <a href="#">Pricing</a>
          </vs-navbar-item>
          <vs-navbar-item index="1">
            <a href="#">Our Data</a>
          </vs-navbar-item>
          <vs-navbar-item index="2">
            <a href="#">Reviews</a>
          </vs-navbar-item>
          <vs-navbar-item index="3">
            <a href="#">About Us</a>
          </vs-navbar-item>
          <vs-navbar-item index="4" class="loginContent">
            <vs-button color="dark" type="flat" icon-pack="feather" icon="icon-user">Login</vs-button>
            <a href="#" class="headerLogin">Login</a>
          </vs-navbar-item>
          <vs-navbar-item index="5">
            <vs-button class="startFreeTrial" color="primary" type="filled">Start Free Trial</vs-button>
            <a href="#" class="headerLogin">Start Free Trial</a>
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
          logo: "",
        },
        {
          socialMedia: "Data Enrichment",
          logo: "",
        },
        {
          socialMedia: "Chrome Extension",
          logo: "",
        },
        {
          socialMedia: "API",
          logo: "",
        },
        {
          socialMedia: "Email Verification",
          logo: "",
        },
        {
          socialMedia: "Technographics",
          logo: "",
        },
        {
          socialMedia: "Email Finder",
          logo: "",
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
      if (this._routerRoot._route.path === "/pages/home") {
        this.scowComp = 1;
      } else {
        this.scowComp = 0;
      }
    }
  }
})
</script>


<style>
  .vs-con-items {
    margin-right: auto;
    margin-left: 6%;
  }
  .vs-navbar--title {
    display: flex;
    justify-content: flex-end;
  }
  .vs-list {
    padding: 8px;
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