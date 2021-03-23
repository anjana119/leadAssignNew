<template>
    <vx-card style="background-color: rgb(255 255 255 / 5%); height: 100%;" title="">
        
<!-- top header start -->
        
        <div class="headerInPreview">
            <vs-dropdown vs-custom-content vs-trigger-click style="">
                <a class="flex items-center anqurTagAsBtn" href.prevent>
                    <span style="curser: pointer; color: black;">{{ checkBox1[0] }} Preview</span>
                    <feather-icon icon="ChevronDownIcon" svgClasses="h-4 w-4 ml-1" style="color: black;" />
                </a>
                <vs-dropdown-menu class="dropdown-login">
                    <vs-list>
                        <transition-group>
                            <vs-list-item class="list-item" v-for="listItem in list" :key="listItem.socialMedia" :title="listItem.socialMedia">
                                <vs-checkbox class="ml-5" v-model="checkBox1" :vs-value="listItem.socialMedia" @change="handleSocialType(listItem.socialMedia)" />
                            </vs-list-item>
                        </transition-group>
                    </vs-list>
                </vs-dropdown-menu>
            </vs-dropdown>
        </div>

<!-- top header end -->

        <vx-card style="width: 75%; margin-top: 20px; margin-left: auto; margin-right: auto;">
            
<!-- header start -->
            
            <div class="header">
                <ul class="faq-supporters">
                    <li class="">
                        <div class="flex items-center">
                            <vs-avatar class="mr-3" src="https://zephoria.com/wp-content/uploads/2015/05/zephoria_thumbnail_transparency_250.jpg" size="35px" />
                            <div class="leading-tight">
                                <p class="font-semibold">
                                    Falken Tire
                                    <span v-if="showHeaderLocation === 1"> is at </span>
                                    <span class="spanTagInLocationHeader" v-if="showHeaderLocation === 1">
                                        {{ locationName.countryName }}.
                                    </span>
                                </p>
                                <small>
                                    Just now
                                    <small style="font-size: 11px;" class="headerLocationTag" v-if="showHeaderLocation === 1">
                                        {{ locationName.countryCode }}.
                                    </small>
                                </small>
                            </div>
                        </div>
                    </li>
                </ul>
            </div>

<!-- header end -->

            <vs-divider />
            <div class="body">

<!-- body text content start -->

                <div class="contentBodyView" :style="object.imageArray.length === 0 ? object.chosedBackGroundAnimation : null" v-html="object.content" />
                
<!-- body text content end -->

<!-- body image view start -->

                <!-- 1 image or video -->
                <div v-if="showImageAndVideoView === 1">
                    <div v-if="object.imageArray.length === 1">
                        <img v-if="object.imageFileArray[0].type.includes('image')" :src="object.imageArray[0]" alt="latest-upload" class="rounded user-latest-image responsive singleImage">
                        <video v-if="object.imageFileArray[0].type.includes('video')" controls class="singleVideo">
                            <source :src="object.imageArray[0]" type="video/mp4">
                        </video>
                    </div>

                    <!-- 2 images or videos -->
                    <div v-if="object.imageArray.length === 2">
                        <div class="vx-row">
                            <div class="vx-col sm:w-1/2 w-full" style="padding: 2px;" v-for="(item, index) in object.imageArray" :key="index">
                                <img v-if="object.imageFileArray[index].type.includes('image')" :src="item" alt="latest-upload" class="rounded user-latest-image responsive twoImages">
                                <video v-if="object.imageFileArray[index].type.includes('video')" controls class="twoVideos">
                                    <source :src="item" type="video/mp4">
                                </video>
                            </div>
                        </div>
                    </div>

                    <!-- 3 images or videos -->
                    <div v-if="object.imageArray.length === 3">
                        <div class="vx-row">
                            <div class="vx-col sm:w-1/2 w-full" style="padding: 2px;">
                                <img v-if="object.imageFileArray[0].type.includes('image')" :src="object.imageArray[0]" alt="latest-upload" class="rounded user-latest-image responsive threeImagesFirstCol">
                                <video v-if="object.imageFileArray[0].type.includes('video')" controls class="threeVideosFirstCol">
                                    <source :src="object.imageArray[0]" type="video/mp4">
                                </video>
                            </div>
                            <div class="vx-col sm:w-1/2 w-full" style="padding: 2px;">
                                <div class="vx-row" v-for="(item, index) in object.imageArray" :key="index">
                                    <div class="vx-col w-full" style="padding: 2px;">
                                        <img v-if="index !== 0 && object.imageFileArray[index].type.includes('image')" :src="item" alt="latest-upload" class="rounded user-latest-image responsive threeImagesSecondCol">
                                        <video v-if="index !== 0 && object.imageFileArray[index].type.includes('video')" controls class="threeVideosSecondCol">
                                            <source :src="item" type="video/mp4">
                                        </video>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- 4 images or videos -->
                    <div v-if="object.imageArray.length === 4">
                        <div class="vx-row">
                            <div class="vx-col sm:w-1/2 w-full" style="padding: 2px;">
                                <div class="vx-row" v-for="(item, index) in object.imageArray" :key="index">
                                    <div class="vx-col w-full" style="padding: 2px;">
                                        <img v-if="index !== 2 && index !== 3 && object.imageFileArray[index].type.includes('image')" :src="item" alt="latest-upload" class="rounded user-latest-image responsive fourImagesFirstCol">
                                    </div>
                                    <video v-if="index !== 2 && index !== 3 && object.imageFileArray[index].type.includes('video')" controls class="fourVideosFirstCol">
                                        <source :src="item" type="video/mp4">
                                    </video>
                                </div>
                            </div>
                            <div class="vx-col sm:w-1/2 w-full" style="padding: 2px;">
                                <div class="vx-row" v-for="(item, index) in object.imageArray" :key="index">
                                    <div class="vx-col w-full" style="padding: 2px;">
                                        <img v-if="index !== 0 && index !== 1 && object.imageFileArray[index].type.includes('image')" :style="index === 2 ? 'margin-top: -8px;' : 'margin-top: 0px;'" :src="item" alt="latest-upload" class="rounded user-latest-image responsive fourImagesSecondCol">
                                    </div>
                                    <video v-if="index !== 0 && index !== 1 && object.imageFileArray[index].type.includes('video')" controls :style="index === 2 ? 'margin-top: -8px;' : 'margin-top: 0px;'" class="fourVideosSecondCol">
                                        <source :src="item" type="video/mp4">
                                    </video>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- more than 4 images or videos -->
                    <div v-if="object.imageArray.length > 4">
                        <div class="vx-row">
                            <div class="vx-col sm:w-1/2 w-full" style="padding: 2px;">
                                <div class="vx-row" v-for="(item, index) in object.imageArray" :key="index">
                                    <div class="vx-col w-full" style="padding: 2px;">
                                        <img v-if="index === 0 || index === 1" v-show="object.imageFileArray[index].type.includes('image')" :src="item" alt="latest-upload" class="rounded user-latest-image responsive moreThanFourImagesFirstCol">
                                        <video v-if="index === 0 || index === 1" v-show="object.imageFileArray[index].type.includes('video')" controls class="moreThanFourVideosFirstCol">
                                            <source :src="item" type="video/mp4">
                                        </video>
                                    </div>
                                </div>
                            </div>
                            <div class="vx-col sm:w-1/2 w-full" style="padding: 2px;">
                                <div class="vx-row" v-for="(item, index) in object.imageArray" :key="index">
                                    <div class="vx-col w-full" style="padding: 2px;">
                                        <img v-if="index === 2 || index === 3" v-show="object.imageFileArray[index].type.includes('image')" :style="index === 2 ? 'margin-top: -8px;' : 'margin-top: 0px;'" :src="item" alt="latest-upload" class="rounded user-latest-image responsive moreThanFourImagesSecondCol">
                                        <video v-if="index === 2 || index === 3" v-show="object.imageFileArray[index].type.includes('video')" controls class="moreThanFourVideosSecondCol">
                                            <source :src="item" type="video/mp4">
                                        </video>
                                    </div>
                                </div>
                            </div>
                            <div class="imageArrayAdditioanlCount">
                                +{{ object.imageArray.length - 4 }}
                            </div>
                        </div>
                    </div>
                </div>

<!-- body image view end -->

<!-- body google map view start -->

                <div v-if="showGoogleMapView === 1">
                    <GmapMap
                        :center="center"
                        :zoom="7"
                        map-type-id="terrain"
                        style="width: 100%; height: 400px"
                    >
                        <GmapMarker
                            :key="index"
                            v-for="(m, index) in markers"
                            :position="m.position"
                            :clickable="true"
                            :draggable="true"
                            @click="center=m.position"
                        />
                    </GmapMap>
                </div>

<!-- body google map view end -->

            </div>

<!-- footer start -->

            <div class="footer">
                <div class="vx-row">
                    <div class="vx-col sm:w-1/12 md:w-1/3 lg:w-1/3 previewBottomClass">
                        <vs-button disabled class="previewActionFooterBtn" color="primary" type="border" icon-pack="feather" icon="icon-thumbs-up">Like</vs-button>
                    </div>
                    <div class="vx-col sm:w-1/12 md:w-1/3 lg:w-1/3 previewBottomClass">
                        <vs-button disabled class="previewActionFooterBtn" color="primary" type="border" icon-pack="feather" icon="icon-message-square">Comment</vs-button>
                    </div>
                    <div class="vx-col sm:w-1/12 md:w-1/3 lg:w-1/3 previewBottomClass">
                        <vs-button disabled class="previewActionFooterBtn" color="primary" type="border" icon-pack="feather" icon="icon-corner-up-right">Share</vs-button>
                    </div>
                </div>
            </div>

<!-- footer end -->

        </vx-card>
    </vx-card>
</template>

<script>
import socialEditors from '../post-input/socialEditors.vue';
export default {
    components: {
        socialEditors
    },
    props: {
        postData: {
            type: Object,
            default: null
        },
        positionCenter: {
            type: Object,
            default: null
        },
        countryName: {
            type: String,
            default: null
        },
        locationMarkers: {
            type: Array,
            default: null
        },
        visibility: {
            type: String,
            default: null
        }
    },
    data() {
        return {
            showHeaderLocation: 0,
            showGoogleMapView: 0,
            showImageAndVideoView: 0,
            object: {},
            showComp: 0,
            center: {},
            markers: [],
            showPreview: 0,
            locationName: {},
            checkBox1: ["Facebook"],
            list: [
                {
                    socialMedia: "Facebook",
                    logo: "https://cdn3.iconfinder.com/data/icons/capsocial-round/500/facebook-512.png",
                },
                {
                    socialMedia: "Instagram",
                    logo: "https://i.pinimg.com/736x/c8/95/2d/c8952d6e421a83d298a219edee783167.jpg",
                }
            ]
        }
    },
    watch: {
        postData: {
            handler(val) {
                if (val instanceof Object) {
                    val.imageArray.length !== 0 ? this.showComp = 1 : this.showComp = 0;
                    this.object = val;
                }
            },
            immediate: true,
            deep: true
        },
        positionCenter: {
            handler(obj) {
                if (obj instanceof Object) {
                    this.showComp = 1;
                    this.center = obj;
                } else {
                    this.showComp = 0;
                }
            },
            immediate: true,
            deep: true
        },
        locationMarkers: {
            handler(arr) {
                if (arr.length !== 0) {
                    this.showComp = 1;
                    this.locationName = arr[0];
                    this.markers.push(arr[0].position);
                } else {
                    this.showComp = 0;
                }
            },
            immediate: true,
            deep: true
        },
        visibility: {
            handler(str) {
                if (str !== "") {
                    if (str === "location") {
                        if (this.object.imageArray.length === 0) {
                            this.showGoogleMapView = 1;     // ------------- show google map view --------------
                            this.showHeaderLocation = 0;
                            this.showImageAndVideoView = 0;
                        } else {
                            this.showGoogleMapView = 0;
                            this.showHeaderLocation = 1;     // ------------- show location tag in header --------------
                            this.showImageAndVideoView = 1;
                        }

                    } else {
                        this.showImageAndVideoView = 1;     // ------------- show image/video view --------------
                        if (this.showGoogleMapView === 1) {
                            this.showGoogleMapView = 0;
                            this.showHeaderLocation = 1;
                        } else {
                            if (this.showHeaderLocation === 1) {
                                this.showHeaderLocation = 1;
                                this.showGoogleMapView = 0;
                            }
                        }
                    }
                }
            },
            immediate: true,
            deep: true
        }
    },
    methods: {
        handleSocialType(val) {
            this.checkBox1 = [];
            this.checkBox1.push(val);
        },
        handleremoveImage(index) {
            this.object.imageArray.splice(index, 1);
            this.object.imageFileArray.splice(index, 1);
            this.object.imageFileArray.length === 0 ? this.showComp = 0 : null;
        }
    }
}
</script>
<style scoped>
.contentBodyView {
    padding: 10px 20px 10px 20px;
    border-radius: 6px;
    max-height: 300px;
    overflow: auto;
}
.countMore {
    padding: 50px 50px 50px 50px;
    position: relative;
    bottom: 155px;
    left: 495px;
    color: white;
    font-size: 25px;
    font-weight: bold;
    background: transparent;
}
.fbPostImage {
    height: 350px;
    border-radius: 6px;
    margin-top: 15px;
}
.previewBottomClass {
    display: flex;
    justify-content: center;
}
.previewActionFooterBtn {
    background: white !important;
    border: 1px solid white !important;
    color: rgb(53, 53, 53) !important;
    font-weight: 500;
    padding-left: 75px !important;
    padding-right: 75px !important;
}
.cloaseBtnDiv {
    display: flex;
    justify-content: flex-end;
}
.closeBtn {
    position: relative;
    top: 45px;
    border: none;
    color: white !important;
    right: 6px;
}
.headerInPreview {
    border: 1px solid rgba(0, 0, 0, 0.15);
    padding: 22px;
    margin-left: -21px;
    margin-right: -21px;
    margin-top: -21px;
}
.anqurTagAsBtn {
    padding: 10px 25px 10px 25px;
    background: #e4e4e4;
    border-radius: 5px;
}
.anqurTagAsBtn:hover {
    background: #d6d6d6;
}
.footer {
    margin-top: 30px;
    margin-bottom: -6px;
}
.imageArrayAdditioanlCount {
    margin-left: auto;
    color: white;
    position: relative;
    right: 112px;
    top: -173px;
    margin-bottom: -75px;
    font-size: 30px;
    font-weight: bold;
    padding: 15px;
}
.headerLocationTag, .spanTagInLocationHeader {
    color: rgb(65 135 241);
}
.singleImage {
    height: 200px;
    width: 550px;
    object-fit: cover;
}
.singleVideo {
    width: 555px;
    height: 200px;
    margin-bottom: 12px;
    background: #efefef;
    object-fit: cover;
}
.twoImages {
    height: 200px;
    width: 282px;
    object-fit: cover;
}
.twoVideos {
    width: 285px;
    height: 200px;
    margin-bottom: 12px;
    background: #efefef;
    object-fit: cover;
}
.threeImagesFirstCol {
    width: 273px;
    height: 411px;
    padding-top: 6px;
    object-fit: cover;
}
.threeImagesSecondCol {
    height: 200px;
    width: 298px;
    object-fit: cover;
}
.threeVideosFirstCol {
    width: 270px;
    height: 400px;
    background: #efefef;
    margin-top: 27px;
    object-fit: cover;
}
.threeVideosSecondCol {
    width: 285px;
    height: 200px;
    margin-top: 20px;
    margin-bottom: -28px;
    background: #efefef;
    object-fit: cover;
}
.fourImagesFirstCol {
    height: 200px;
    width: 275px;
    margin-left: 12px;
    object-fit: cover;
}
.fourImagesSecondCol {
    height: 200px;
    width: 295px;
    margin-left: 3px;
    object-fit: cover;
}
.fourVideosFirstCol {
    width: 280px;
    height: 200px;
    margin-left: 20px;
    margin-bottom: 0px;
    background: #efefef;
    object-fit: cover;
}
.fourVideosSecondCol {
    width: 280px;
    height: 200px;
    margin-left: 15px;
    background: #efefef;
    object-fit: cover;
}
.moreThanFourImagesFirstCol {
    height: 200px;
    width: 288px;
    margin-left: 12px;
    object-fit: cover;
}
.moreThanFourImagesSecondCol {
    height: 200px;
    width: 286px;
    margin-left: 13px;
    object-fit: cover;
}
.moreThanFourVideosFirstCol {
    width: 292px;
    height: 200px;
    margin-left: 10px;
    margin-bottom: -8px;
    background: #efefef;
    object-fit: cover;
}
.moreThanFourVideosSecondCol {
    width: 285px;
    height: 200px;
    margin-left: 15px;
    margin-top: -8px;
    background: #efefef;
    object-fit: cover;
}
@media only screen and (max-width: 1440px) {
    .singleImage {
        width: 355px;
    }
    .singleVideo {
        width: 355px;
        margin-bottom: 0px;
    }
    .twoImages {
        height: 215px;
        width: 188px;
    }
    .twoVideos {
        width: 188px;
        height: 215px;
        margin-bottom: 0px;
    }
    .threeImagesFirstCol {
        width: 175px;
        height: 410px;
    }
    .threeImagesSecondCol {
        width: 200px;
        height: 200px;
    }
    .threeVideosFirstCol {
        width: 186px;
        height: 402px;
        margin-top: 26px;
    }
    .threeVideosSecondCol {
        width: 192px;
        height: 200px;
        margin-left: 10px;
        margin-top: 20px;
        margin-bottom: -28px;
    }
    .fourImagesFirstCol {
        width: 186px;
    }
    .fourImagesSecondCol {
        width: 190px;
        margin-left: 10px;
        margin-top: -8px;
    }
    .fourVideosFirstCol {
        width: 184px;
    }
    .fourVideosSecondCol {
        width: 184px;
    }
    .moreThanFourImagesFirstCol {
        width: 190px;
    }
    .moreThanFourImagesSecondCol {
        width: 188px;
    }
    .imageArrayAdditioanlCount {
        top: -165px;
        right: 63px;
    }
    .moreThanFourVideosFirstCol {
        width: 194px;
    }
    .moreThanFourVideosSecondCol {
        width: 186px;
    }
}
@media only screen and (max-width: 1280px) {
    .singleImage {
        width: 408px;
    }
    .singleVideo {
        width: 408px;
        margin-bottom: 0px;
    }
    .twoImages {
        height: 180px;
        width: 214px;
    }
    .twoVideos {
        width: 214px;
        height: 180px;
    }
    .threeImagesFirstCol {
        width: 202px;
    }
    .threeImagesSecondCol {
        width: 226px;
    }
    .threeVideosFirstCol {
        width: 212px;
    }
    .threeVideosSecondCol {
        width: 216px;
    }
    .fourImagesFirstCol {
        width: 212px;
    }
    .fourImagesSecondCol {
        width: 218px;
    }
    .fourVideosFirstCol {
        width: 210px;
    }
    .fourVideosSecondCol {
        width: 210px;
    }
    .moreThanFourImagesFirstCol {
        width: 215px;
    }
    .moreThanFourImagesSecondCol {
        width: 215px;
    }
    .imageArrayAdditioanlCount {
        right: 75px;
    }
    .moreThanFourVideosFirstCol {
        width: 220px;
    }
    .moreThanFourVideosSecondCol {
        width: 214px;
    }
}
@media only screen and (max-width: 1024px) {
    .singleImage {
        width: 355px;
    }
    .singleVideo {
        width: 350px;
        margin-bottom: 0px;
    }
    .twoImages {
        height: 110px;
        width: 185px;
    }
    .twoVideos {
        width: 185px;
        height: 110px;
    }
    .threeImagesFirstCol {
        width: 175px;
    }
    .threeImagesSecondCol {
        width: 200px;
    }
    .threeVideosFirstCol {
        width: 183px;
        height: 300px;
    }
    .threeVideosSecondCol {
        width: 188px;
        height: 149px;
    }
    .fourImagesFirstCol {
        width: 184px;
    }
    .fourImagesSecondCol {
        width: 188px;
    }
    .fourVideosFirstCol {
        width: 180px;
    }
    .fourVideosSecondCol {
        width: 180px;
    }
    .moreThanFourImagesFirstCol {
        width: 187px;
    }
    .moreThanFourImagesSecondCol {
        width: 185px;
    }
    .imageArrayAdditioanlCount {
        right: 60px;
    }
    .moreThanFourVideosFirstCol {
        width: 187px;
    }
    .moreThanFourVideosSecondCol {
        width: 190px;
    }
}
@media only screen and (max-width: 768px) {
    .singleImage {
        width: 240px;
        height: 135px;
    }
    .singleVideo {
        width: 240px;
        height: 140px;
        margin-bottom: 0px;
    }
    .twoImages {
        height: 76px;
        width: 130px;
    }
    .twoVideos {
        width: 130px;
        height: 75px;
    }
    .threeImagesFirstCol {
        width: 116px;
    }
    .threeImagesSecondCol {
        width: 142px;
    }
    .threeVideosFirstCol {
        width: 125px;
        height: 160px;
        margin-bottom: -30px;
    }
    .threeVideosSecondCol {
        width: 130px;
        height: 80px;
    }
    .fourImagesFirstCol {
        width: 128px;
    }
    .fourImagesSecondCol {
        width: 130px;
        margin-top: -8px;
    }
    .fourVideosFirstCol {
        width: 122px;
    }
    .fourVideosSecondCol {
        width: 122px;
    }
    .moreThanFourImagesFirstCol {
        width: 130px;
        height: 130px;
    }
    .moreThanFourImagesSecondCol {
        width: 128px;
        height: 130px;
    }
    .imageArrayAdditioanlCount {
        top: -133px;
        right: 35px;
    }
    .moreThanFourVideosFirstCol {
        width: 128px;
    }
    .moreThanFourVideosSecondCol {
        width: 132px;
    }
}
@media only screen and (max-width: 540px) {
    .singleImage {
        width: 308px;
        height: 160px;
    }
    .singleVideo {
        width: 305px;
        height: 172px;
        margin-bottom: 0px;
    }
    .twoImages {
        height: 175px;
        width: 330px;
    }
    .twoVideos {
        width: 330px;
        height: 185px;
    }
    .threeImagesFirstCol {
        width: 330px;
        margin-bottom: -6px;
    }
    .threeImagesSecondCol {
        width: 330px;
        height: 155px;
        margin-left: 12px;
    }
    .threeVideosFirstCol {
        width: 330px;
        height: 300px;
    }
    .threeVideosSecondCol {
        width: 333px;
        height: 110px;
    }
    .fourImagesFirstCol {
        width: 330px;
    }
    .fourImagesSecondCol {
        width: 330px;
        margin-left: 12px;
    }
    .fourVideosFirstCol {
        width: 320px;
    }
    .fourVideosSecondCol {
        width: 320px;
        margin-left: 20px;
    }
    .moreThanFourImagesFirstCol {
        width: 330px;
    }
    .moreThanFourImagesSecondCol {
        width: 330px;
    }
    .imageArrayAdditioanlCount {
        right: 133px;
    }
    .moreThanFourVideosFirstCol {
        width: 335px;
    }
    .moreThanFourVideosSecondCol {
        width: 335px;
    }
}
@media only screen and (max-width: 414px) {
    .singleImage {
        width: 212px;
        height: 115px;
    }
    .singleVideo {
        width: 215px;
        height: 122px;
        margin-bottom: 0px;
    }
    .twoImages {
        height: 132px;
        width: 236px;
    }
    .twoVideos {
        width: 233px;
        height: 135px;
    }
    .threeImagesFirstCol {
        width: 235px;
        height: 210px;
        margin-bottom: -5px;
    }
    .threeImagesSecondCol {
        width: 237px;
        height: 100px;
        margin-left: 10px;
    }
    .threeVideosFirstCol {
        width: 233px;
        height: 270px;
        margin-bottom: -30px;
    }
    .threeVideosSecondCol {
        width: 235px;
        height: 120px;
    }
    .fourImagesFirstCol {
        width: 234px;
    }
    .fourImagesSecondCol {
        width: 236px;
    }
    .fourVideosFirstCol {
        width: 225px;
    }
    .fourVideosSecondCol {
        width: 225px;
        margin-left: 20px;
    }
    .moreThanFourImagesFirstCol {
        width: 238px;
    }
    .moreThanFourImagesSecondCol {
        width: 236px;
    }
    .imageArrayAdditioanlCount {
        right: 88px;
    }
    .moreThanFourVideosFirstCol {
        width: 240px;
    }
    .moreThanFourVideosSecondCol {
        width: 240px;
        margin-left: 10px;
    }
}
@media only screen and (max-width: 375px) {
    .singleImage {
        width: 185px;
        height: 100px;
    }
    .singleVideo {
        width: 185px;
        height: 105px;
        margin-bottom: 0px;
    }
    .twoImages {
        height: 116px;
        width: 208px;
    }
    .twoVideos {
        width: 208px;
        height: 120px;
    }
    .threeImagesFirstCol {
        width: 208px;
    }
    .threeImagesSecondCol {
        width: 208px;
        height: 100px;
        margin-left: 12px;
    }
    .threeVideosFirstCol {
        width: 210px;
        margin-left: -2px;
        height: 300px;
    }
    .threeVideosSecondCol {
        width: 215px;
        height: 115px;
    }
    .fourImagesFirstCol {
        width: 208px;
    }
    .fourImagesSecondCol {
        width: 210px;
    }
    .fourVideosFirstCol {
        width: 195px;
    }
    .fourVideosSecondCol {
        width: 195px;
        margin-left: 20px;
    }
    .moreThanFourImagesFirstCol {
        width: 208px;
    }
    .moreThanFourImagesSecondCol {
        width: 208px;
    }
    .imageArrayAdditioanlCount {
        right: 70px;
    }
    .moreThanFourVideosFirstCol {
        width: 212px;
    }
    .moreThanFourVideosSecondCol {
        width: 212px;
        margin-left: 10px;
    }
}
@media only screen and (max-width: 360px) {
    .singleImage {
        width: 173px;
        height: 82px;
    }
    .singleVideo {
        width: 175px;
        height: 100px;
        margin-bottom: 0px;
    }
    .twoImages {
        height: 108px;
        width: 196px;
    }
    .twoVideos {
        width: 197px;
        height: 110px;
    }
    .threeImagesFirstCol {
        width: 198px;
        height: 210px;
        margin-bottom: -5px;
    }
    .threeImagesSecondCol {
        width: 200px;
        height: 100px;
        margin-left: 10px;
    }
    .threeVideosFirstCol {
        width: 200px;
        margin-left: -2px;
        height: 300px;
    }
    .threeVideosSecondCol {
        width: 200px;
        height: 115px;
    }
    .fourImagesFirstCol {
        width: 198px;
    }
    .fourImagesSecondCol {
        width: 200px;
    }
    .fourVideosFirstCol {
        width: 185px;
    }
    .fourVideosSecondCol {
        width: 185px;
        margin-left: 20px;
    }
    .moreThanFourImagesFirstCol {
        width: 198px;
    }
    .moreThanFourImagesSecondCol {
        width: 198px;
    }
    .imageArrayAdditioanlCount {
        right: 63px;
    }
    .moreThanFourVideosFirstCol {
        width: 200px;
    }
    .moreThanFourVideosSecondCol {
        width: 200px;
        margin-left: 10px;
    }
}
@media only screen and (max-width: 320px) {
    .singleImage {
        width: 145px;
        height: 82px;
    }
    .singleVideo {
        width: 145px;
        height: 85px;
        margin-bottom: 0px;
    }
    .twoImages {
        height: 90px;
        width: 165px;
    }
    .twoVideos {
        width: 167px;
        height: 100px;
    }
    .threeImagesFirstCol {
        width: 170px;
    }
    .threeImagesSecondCol {
        width: 170px;
        height: 100px;
    }
    .threeVideosFirstCol {
        width: 170px;
        margin-left: -2px;
        height: 300px;
    }
    .threeVideosSecondCol {
        width: 170px;
        height: 115px;
    }
    .fourImagesFirstCol {
        width: 167px;
    }
    .fourImagesSecondCol {
        width: 170px;
    }
    .fourVideosFirstCol {
        width: 155px;
    }
    .fourVideosSecondCol {
        width: 155px;
    }
    .moreThanFourImagesFirstCol {
        width: 168px;
    }
    .moreThanFourImagesSecondCol {
        width: 166px;
    }
    .imageArrayAdditioanlCount {
        right: 48px;
    }
    .moreThanFourVideosFirstCol {
        width: 170px;
    }
    .moreThanFourVideosSecondCol {
        width: 170px;
    }
}
@media only screen and (max-width: 280px) {
    .singleImage {
        width: 115px;
        height: 65px;
    }
    .singleVideo {
        width: 110px;
        height: 60px;
        margin-bottom: 0px;
    }
    .twoImages {
        height: 75px;
        width: 136px;
    }
    .twoVideos {
        width: 137px;
        height: 77px;
    }
    .threeImagesFirstCol {
        width: 138px;
    }
    .threeImagesSecondCol {
        width: 138px;
        height: 100px;
        margin-left: 12px;
    }
    .threeVideosFirstCol {
        width: 140px;
        height: 210px;
    }
    .threeVideosSecondCol {
        width: 140px;
        height: 80px;
    }
    .fourImagesFirstCol {
        width: 138px;
    }
    .fourImagesSecondCol {
        width: 138px;
    }
    .fourVideosFirstCol {
        width: 125px;
    }
    .fourVideosSecondCol {
        width: 125px;
    }
    .moreThanFourImagesFirstCol {
        width: 138px;
    }
    .moreThanFourImagesSecondCol {
        width: 136px;
    }
    .imageArrayAdditioanlCount {
        right: 33px;
    }
    .moreThanFourVideosFirstCol {
        width: 140px;
    }
    .moreThanFourVideosSecondCol {
        width: 140px;
    }
}
</style>