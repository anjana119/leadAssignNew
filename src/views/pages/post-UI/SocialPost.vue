<template>
    <div class="vx-row mb-6">
        <div class="vx-col sm:w-2/5 w-full">
            <social-editors
                @handleInput="handleInput"
                @handleFileUploadImage="handleFileUploadImage"
                @handleLocationControl="handleLocationControl"
            />
        </div>
        <div class="vx-col sm:w-3/5 w-full">
            <facebook-preview
                :postData="postData"
                :positionCenter="positionCenter"
                :countryName="countryName"
                :locationMarkers="locationMarkers"
                :visibility="visibility"
            />
        </div>
    </div>
</template>
<script>
import socialEditors from './post-input/socialEditors.vue'
import FacebookPreview from './post-preview/FacebookPreview.vue'
export default {
    components: {
        socialEditors,
        FacebookPreview
    },
    data() {
        return {
            positionCenter: {},
            locationMarkers: [],
            visibility: "",
            conditionMode: "",
            postData: {
                date:  "",
                content: "" ,
                chosedBackGroundAnimation: "",
                imageFileArray: [],
                imageArray: []
            }
        };
    },
    methods: {
        handleInput(con, val) {
            con === "quill" ? this.postData.content = val : this.postData.chosedBackGroundAnimation = val;
        },
        handleFileUploadImage(file, fileReader, condition) {
            this.postData.imageFileArray = file;
            this.postData.imageArray = fileReader;
            this.visibility = condition;
        },
        handleLocationControl(center, markers, condition1) {
            this.positionCenter = center;
            this.locationMarkers = markers;
            this.visibility = condition1;
        }
    }
}
</script>

<style scoped>

</style>