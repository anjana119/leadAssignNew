<template>
    <vx-card title="Instagram Preview">
        <div>
            <swiper :options="swiperOption" :dir="$vs.rtl ? 'rtl' : 'ltr'" :key="$vs.rtl">
                <swiper-slide v-for="(img, index) in object.imageArray" :key="index">
                    <img style="height: 450px;" class="responsive" :src="img" alt="banner">
                </swiper-slide>
                <div class="swiper-pagination" style="position: relative; top: 5px;" slot="pagination"></div>
          </swiper>
        </div>
        <vs-divider></vs-divider>
        <div class="vx-row">
            <div class="vx-col sm:w-1/12 md:w-1/4 lg:w-1/4 previewBottomClass">
                <vs-button class="previewActionFooterBtn" color="primary" type="border" icon-pack="feather" icon="icon-heart"></vs-button>
            </div>
            <div class="vx-col sm:w-1/12 md:w-1/4 lg:w-1/4 previewBottomClass">
                <vs-button class="previewActionFooterBtn" color="primary" type="border" icon-pack="feather" icon="icon-message-circle"></vs-button>
            </div>
            <div class="vx-col sm:w-1/12 md:w-1/4 lg:w-1/4 previewBottomClass">
                <vs-button class="previewActionFooterBtn" color="primary" type="border" icon-pack="feather" icon="icon-send"></vs-button>
            </div>
            <div class="vx-col sm:w-1/12 md:w-1/4 lg:w-1/4 previewBottomClass">
                <vs-button class="previewActionFooterBtn" color="primary" type="border" icon-pack="feather" icon="icon-bookmark"></vs-button>
            </div>
        </div>
    </vx-card>
</template>

<script>
import 'swiper/dist/css/swiper.min.css'
import { swiper, swiperSlide } from 'vue-awesome-swiper'
export default {
    props: {
        postData: {
            type: Object,
            default: null
        }
    },
    components: {
        swiper,
        swiperSlide
    },
    data() {
        return {
            object: {},
            showComp: 0,
            swiperOption: {
                pagination: {
                    el: '.swiper-pagination'
                }
            }
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
        }
    },
    methods: {
        handleremoveImage(index) {
            this.object.imageArray.splice(index, 1);
            this.object.imageFileArray.splice(index, 1);
            this.object.imageFileArray.length === 0 ? this.showComp = 0 : null;
        }
    }
}
</script>
<style scoped>
.previewBottomClass {
    display: flex;
    justify-content: center;
}
.previewActionFooterBtn {
    background: white !important;
    border: 1px solid white !important;
    color: gray !important;
    font-weight: 500;
    padding-left: 75px !important;
    padding-right: 75px !important;
}
.previewActionFooterBtn:hover {
    background: #efefef !important;
    font-weight: 600;
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
</style>