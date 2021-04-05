<template>
    <div style="display: flex; justify-content: center;">
        <div class="vx-row" style="width: 75%;">
            <div class="vx-col w-full sm:w-1/2 md:w-1/2">
                <video-player ref="player" class="media-video-player" :options="playerOptions(media)" />
            </div>
            <div class="vx-col w-full sm:w-1/2 md:w-1/2">
                <h1 class="headerContentSecondPage">
                    Code Red Safety Closed $150,000 in New Business Within the First 60 Days of Using O2OLeads
                </h1>
                <span class="secondContentParagraph">
                    Lorem Ipsum is simply dummy text of the printing and type setting industry. 
                    Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley.
                </span>
                <div>
                    <vs-button class="actionButtonSecondContent" color="danger" type="filled" icon-pack="feather" icon="icon-arrow-up-right" icon-after>
                        View Case Study
                    </vs-button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import { videoPlayer } from 'vue-video-player'
import 'video.js/dist/video-js.css'

export default {
    components: {
        videoPlayer,
    },
    data() {
        return {
            media: { sources: [{ type: "video/mp4", src: "http://vjs.zencdn.net/v/oceans.mp4" }], poster: 'https://goo.gl/xcCsDd' }
        }
    },
    computed: {
        playerOptions() {
            return (media) => {
                return {
                    height: '360',
                    fluid: true,
                    autoplay: false,
                    muted: true,
                    language: 'en',
                    playbackRates: [0.7, 1.0, 1.5, 2.0],
                    sources: media.sources,
                    poster: media.poster,
                }
            }
        }
    },
}
</script>

<style>
    [dir=ltr] .video-js .vjs-big-play-button {
        position: relative !important;
        top: -95px !important;
    }
    .video-js.vjs-fluid, .video-js.vjs-16-9, .video-js.vjs-4-3 {
        display: flex;
        justify-content: center;
        width: 687px;
        height: 433px;
    }
    .headerContentSecondPage {
        text-align: left;
        letter-spacing: 0px;
        font: normal normal medium 45px/55px Poppins;
        color: #142537;
        opacity: 1;
        font-size: 40px;
        margin-bottom: 35px;
    }
    .secondContentParagraph {
        font: normal normal 300 18px/33px Poppins;
        letter-spacing: 0px;
        color: #142537;
        line-height: 28px;
    }
    .actionButtonSecondContent {
        float: inherit;
        font-family: 'Poppins', sans-serif;
        background:#FF0000 !important;
        left: 0px;
        right: 15px;
        top: 75px;
        padding: 15px 40px 15px 40px !important;
    }
</style>