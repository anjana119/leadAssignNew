<template>
    <div>
        <h5>Placements</h5>
        <ul class="faq-supporters mt-4" style="max-height: 275px; overflow: auto;">
            <li v-for="(listItem, index) in list" :key="index" class="mt-4">
                <div class="flex items-center">
                    <vs-checkbox v-model="socialTypeArray" :vs-value="listItem.socialType" @change="handlePlacement(listItem.socialType)" />
                    <vs-avatar class="mr-3" :src="listItem.logo" size="25px" />
                    <div class="leading-tight">
                        <p class="font-semibold">
                            {{ listItem.socialType }}
                        </p>
                    </div>
                </div>
                <vs-divider />
                <ul v-if="listItem.childern.length !== 0" class="faq-supporters ml-5">
                    <li v-for="(item, ind) in listItem.childern" :key="ind">
                        <div class="flex items-center">
                            <vs-checkbox v-model="socialTypeArrayChildren" :vs-value="item.name" />
                            <vs-avatar class="mr-3" :src="item.src" size="25px" />
                            <div class="leading-tight">
                                <p class="font-semibold">
                                    {{ item.name }}
                                    <vs-avatar
                                        style="position: relative; top: 4px; left: 8px;"
                                        :src="item.type === 'page' ? 'https://i.pinimg.com/originals/4a/f0/c7/4af0c7a139b4a6199d7fb78c207629fa.png' : 'https://img.favpng.com/18/5/20/blue-human-behavior-silhouette-area-communication-png-favpng-wLT3QYknSwc68uu9GAUHGS5FY_t.jpg'"
                                        size="20px"
                                    />
                                </p>
                                <small>{{ item.email }}</small>
                            </div>
                        </div>
                        <vs-divider />
                    </li>
                </ul>
            </li>
        </ul>
        <div class="dropdown-button-container moodDropdown">
            <vs-dropdown>
                <vs-button class="btn-drop btnForDropdown" type="line" color="dark" icon="mood"></vs-button>
                <vs-dropdown-menu position="top">
                    <vs-dropdown-item>
                        <i class="material-icons"> mood </i>
                    </vs-dropdown-item>
                    <vs-dropdown-item>
                        <i class="material-icons"> mood_bad </i>
                    </vs-dropdown-item>
                    <vs-dropdown-item>
                        <i class="material-icons"> sentiment_dissatisfied </i>
                    </vs-dropdown-item>
                    <vs-dropdown-item>
                        <i class="material-icons"> sentiment_satisfied </i>
                    </vs-dropdown-item>
                    <vs-dropdown-item>
                        <i class="material-icons"> sentiment_very_dissatisfied </i>
                    </vs-dropdown-item>
                    <vs-dropdown-item>
                        <i class="material-icons"> sentiment_very_satisfied </i>
                    </vs-dropdown-item>
                </vs-dropdown-menu>
            </vs-dropdown>
        </div>
        <div>
            <h5 style="margin-top: 25px;">Text</h5>
            <quill-editor v-model="content" ref="quillEditorRef"></quill-editor>
        </div>
        <div class="flex flex-wrap mt-5">
            <vs-button @click="handleControlCheck()" style="background: #f7f7f7;" color="dark" type="line" icon-pack="feather" :icon="showComp === false ? 'icon-chevrons-right' : 'icon-chevrons-left'" />
            <div class="btn-group" v-if="showComp === true">
                <vs-button
                    color="dark"
                    type="line"
                    class="buttonGroupChooseColour"
                    style="background: gold;"
                    :style="visibleArrow1 === 0 ? 'border: none;' : 'border: 2px solid;'"
                    @click="handleCheck(1, 'background: gold;')"
                />
                <vs-button
                    color="dark"
                    type="line"
                    class="buttonGroupChooseColour"
                    style="background: #bbbbff;"
                    :style="visibleArrow2 === 0 ? 'border: none;' : 'border: 2px solid;'"
                    @click="handleCheck(2, 'background: #bbbbff;')"
                />
                <vs-button
                    color="dark"
                    type="line"
                    class="buttonGroupChooseColour"
                    style="background: aquamarine;"
                    :style="visibleArrow3 === 0 ? 'border: none;' : 'border: 2px solid;'"
                    @click="handleCheck(3, 'background: aquamarine;')"
                />
                <vs-button
                    color="dark"
                    type="line"
                    class="buttonGroupChooseColour"
                    style="background: oldlace;"
                    :style="visibleArrow4 === 0 ? 'border: none;' : 'border: 2px solid;'"
                    @click="handleCheck(4, 'background: oldlace;')"
                />
                <vs-button
                    color="dark"
                    type="line"
                    class="buttonGroupChooseColour"
                    style="background: darkgray;"
                    :style="visibleArrow5 === 0 ? 'border: none;' : 'border: 2px solid;'"
                    @click="handleCheck(5, 'background: darkgray;')"
                />
                <vs-button
                    color="dark"
                    type="line"
                    class="buttonGroupChooseColour"
                    style="background: #ffac90;"
                    :style="visibleArrow6 === 0 ? 'border: none;' : 'border: 2px solid;'"
                    @click="handleCheck(6, 'background: #ffac90;')"
                />
                <vs-button
                    color="dark"
                    type="line"
                    class="buttonGroupChooseColour"
                    style="background: #66d9ff;"
                    :style="visibleArrow7 === 0 ? 'border: none;' : 'border: 2px solid;'"
                    @click="handleCheck(7, 'background: #66d9ff;')"
                />
                <vs-button
                    color="dark"
                    type="line"
                    class="buttonGroupChooseColour"
                    style="background: #ffa4ff;"
                    :style="visibleArrow8 === 0 ? 'border: none;' : 'border: 2px solid;'"
                    @click="handleCheck(8, 'background: #ffa4ff;')"
                />
                <vs-button
                    color="dark"
                    type="line"
                    class="buttonGroupChooseColour"
                    style="background: mistyrose;"
                    :style="visibleArrow9 === 0 ? 'border: none;' : 'border: 2px solid;'"
                    @click="handleCheck(9, 'background: mistyrose;')"
                />
            </div>
        </div>
        <h5 v-if="arrayFileRead.length !== 0" style="margin-top: 25px; margin-bottom: 25px;">Media</h5>
        <div v-if="arrayFileRead.length !== 0" class="mt-5" style="max-height: 285px; overflow-x: hidden;">
            <div class="vx-row" v-for="(fr, index) in arrayFileRead" :key="index">
                <div class="vx-col w-2/3" style="display: flex; justify-content: flex-start;">
                    <img v-if="arrayFile[index].type.includes('image')" :src="fr" alt="latest-upload" class="rounded user-latest-image responsive imageListInEditor">
                    <video v-if="arrayFile[index].type.includes('video')" controls class="videoListInEditor">
                        <source :src="fr" type="video/mp4">
                    </video>
                    <p class="imageDescription">{{ arrayFile[index].name.split('.')[0] }}</p>
                </div>
                <div class="vx-col w-1/3" style="display: flex; justify-content: center; margin-top: auto; margin-bottom: auto;">
                    <vs-button class="mr-2" color="dark" type="flat" icon-pack="feather" icon="icon-edit-2" />
                    <vs-button color="dark" type="flat" icon-pack="feather" icon="icon-trash-2" @click="handleImageRemove(index)" />
                </div>
            </div>
        </div>
        <div class="mt-5" style="border-radius: 5px; border: 1px solid rgba(0, 0, 0, 0.2) !important;">
            <div style="padding: 20px;">
                <div class="vx-row">
                    <div class="vx-col sm:w-4/4 md:w-1/2 lg:w-1/2">
                        <p style="font-weight: 700; margin-top: 3px;">Add To Your Post</p>
                    </div>
                    <div class="vx-col sm:w-1/3 md:w-3/6 lg:w-3/6 addToPostClass" style="right: 150px;">
                        <vs-input type="file" multiple id="embedfileinput" @change="attachFile" style="display: none;" />
                        <vx-tooltip text="Upload Image" position="bottom">
                            <vs-button @click="handleFileUploadControl" type="flat" style="background: #f7f7f7;" color="dark"  icon-pack="feather" icon="icon-image" />
                        </vx-tooltip>
                    </div>
                    <div class="vx-col sm:w-1/3 md:w-3/6 lg:w-3/6 addToPostClass" style="right: 90px;">
                        <vs-input type="file" multiple id="embedfileinput1" @change="attachFile1" style="display: none;" />
                        <vx-tooltip text="Upload Video" position="bottom">
                            <vs-button @click="handleFileUploadControlVideo" style="background: #f7f7f7;" color="dark" type="flat" icon-pack="feather" icon="icon-video" />
                        </vx-tooltip>
                    </div>
                    <div class="vx-col sm:w-1/3 md:w-3/6 lg:w-3/6 addToPostClass" style="right: 30px;">
                        <vx-tooltip text="Add Location" position="bottom">
                            <vs-button @click="handleLocations()" style="background: #f7f7f7;" color="dark" type="flat" icon-pack="feather" icon="icon-map-pin" />
                        </vx-tooltip>
                    </div>
                </div>
            </div>
        </div>
        <div v-if="showLocationComp === 1" class="mt-5">
            <p class="mb-3">Search Location</p>
            <v-select label="countryName" v-model="selectedLocation" :options="locationList" :dir="$vs.rtl ? 'rtl' : 'ltr'" @input="handleLocationChange(selectedLocation)" />
        </div>
        <div class="mt-5 postNowDiv">
            <vs-button color="primary" type="filled" icon-pack="feather" icon="icon-check">Post Now</vs-button>
        </div>
    </div>
</template>

<script>
import vSelect from 'vue-select'
import Prism from 'vue-prism-component'

import 'quill/dist/quill.core.css'
import 'quill/dist/quill.snow.css'
import 'quill/dist/quill.bubble.css'

import { quillEditor } from 'vue-quill-editor'
export default {
    props: {
        checkBox1: {
            type: Array,
            default: null
        }
    },
    components: {
        quillEditor,
        'v-select': vSelect,
        Prism
    },
    data() {
        return {
            selectedLocation: "",
            center: { lat: 10.0, lng: 10.0 },
            markers: [],
            locationList: [
                {
                    countryCode: "sri jayawardenapura kotte",
                    countryName: "Diyatha Uyana",
                    position: {
                        lat: 6.9271,
                        lng: 79.8612
                    }
                },
                {
                    countryCode: "Nugegoda",
                    countryName: "Urban Wetland Park",
                    position: {
                        lat: 6.8649,
                        lng: 79.8997
                    }
                },
                {
                    countryCode: "Colombo",
                    countryName: "Galle Face",
                    position: {
                        lat: 6.8868,
                        lng: 79.9187
                    }
                },
                {
                    countryCode: "Galle",
                    countryName: "Galle Fort",
                    position: {
                        lat: 6.0535,
                        lng: 80.2210
                    }
                },
                {
                    countryCode: "Colombo",
                    countryName: "Shangri-La Hotel",
                    position: {
                        lat: 6.9186,
                        lng: 79.8470
                    }
                },
                {
                    countryCode: "Kandy",
                    countryName: "Temple of the Sacred Tooth Relic",
                    position: {
                        lat: 7.2906,
                        lng: 80.6337
                    }
                },
                {
                    countryCode: "Colombo",
                    countryName: "Colombo Municipal Council",
                    position: {
                        lat: 6.9157,
                        lng: 79.8636
                    }
                },
                {
                    countryCode: "Nuwara Eliya",
                    countryName: "Lake Gregory",
                    position: {
                        lat: 6.9497,
                        lng: 80.7891
                    }
                }
            ],
            content: "",
            image: null,
            chosedBackGroundAnimation: "",
            showComp: false,
            checkBox1: [],
            list: [
                {
                    socialType: "Facebook",
                    switch: true,
                    logo: "https://cdn3.iconfinder.com/data/icons/capsocial-round/500/facebook-512.png",
                    childern: []
                },
                {
                    socialType: "Instagram",
                    switch: false,
                    logo: "https://i.pinimg.com/736x/c8/95/2d/c8952d6e421a83d298a219edee783167.jpg",
                    childern: []
                }
            ],

            socialTypeArrayChildren: [],
            socialTypeArray: ["Facebook"],
            placements: [],
            arrayFile: [],
            arrayFileRead: [],
            arrayFileVideo: [],
            arrayFileReadVideo: [],
            arrayFileImage: [],
            arrayFileReadImage: [],
            visibleArrow1: 0,
			visibleArrow2: 0,
			visibleArrow3: 0,
			visibleArrow4: 0,
			visibleArrow5: 0,
			visibleArrow6: 0,
			visibleArrow7: 0,
			visibleArrow8: 0,
			visibleArrow9: 0,
            type: "",
            showLocationComp: 0
        }
    },
    watch: {
        checkBox1: {
            handler(val) {
                if (val.length !== 0) {
                    this.placements = val;
                }
            },
            immediate: true,
            deep: true
        },
        content() {
            this.$emit("handleInput", "quill", this.content);
        },
        chosedBackGroundAnimation() {
            this.$emit("handleInput", "color code", this.chosedBackGroundAnimation);
        }
    },
    mounted() {
        this.focusQuillEditor();
    },
    created() {
        this.handlePlacement("Facebook");
    },
    methods: {
        handleLocations() {
            this.showLocationComp = 1;
        },
        handleLocationChange(val) {
            this.markers = [];
            this.markers.push(val);
            this.$emit("handleLocationControl", this.center, this.markers, "location");
        },
        handlePlacement(value) {
            let arr = [
                {
                    name: "Falken Tire",
                    src: "https://zephoria.com/wp-content/uploads/2015/05/zephoria_thumbnail_transparency_250.jpg",
                    email: "essie@vaill.com",
                    type: "page"
                },
                {
                    name: "Nitto Tire USA",
                    src: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSGauqvt8eBJvDaoCabFO_D5mi75aobl3umjA&usqp=CAU",
                    email: "cruz@roudabush.com",
                    type: "group"
                },
                {
                    name: "ADT",
                    src: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR5FoWABvPuShdttvMU2lKHBFY9u6Pxc0l1eQ&usqp=CAU",
                    email: "valerie@pou.com",
                    type: "page"
                },
                {
                    name: "Inner Light Media",
                    src: "https://www.hackingchinese.com/wp-content/uploads/2012/08/yong.png",
                    email: "sue@haakinson.com",
                    type: "group"
                }
            ];
            if (value === "Facebook") {
                this.list[0].childern.length === 0 ? this.list[0].childern = arr : this.list[0].childern = [];
            } else {
                this.list[1].childern.length === 0 ? this.list[1].childern = arr : this.list[1].childern = [];
            }
        },
        handleImageRemove(index) {
            this.arrayFile.splice(index, 1);
            this.arrayFileRead.splice(index, 1);
            this.arrayFileImage.splice(index, 1);
            this.arrayFileVideo.splice(index, 1);
            this.arrayFileReadImage.splice(index, 1);
            this.arrayFileReadVideo.splice(index, 1);
            this.$emit("handleFileUploadImage", this.arrayFile, this.arrayFileRead, "image");
        },
        focusQuillEditor() {
            this.$refs.quillEditorRef.$el.children[1].firstChild.dataset.placeholder = "";
        },
        handleFileUploadControl() {
            document.getElementById("embedfileinput").click();
            this.type = "image";
        },
        handleFileUploadControlVideo() {
            document.getElementById("embedfileinput1").click();
            this.type = "video";
        },
        handleControlCheck() {
            this.showComp = !this.showComp;
            this.showComp === false ? this.chosedBackGroundAnimation = "" : null;
            this.visibleArrow1 = 0;
            this.visibleArrow2 = 0;
            this.visibleArrow3 = 0;
            this.visibleArrow4 = 0;
            this.visibleArrow5 = 0;
            this.visibleArrow6 = 0;
            this.visibleArrow7 = 0;
            this.visibleArrow8 = 0;
            this.visibleArrow9 = 0;
        },
        handleCheck(value, colorCode) {
			this.chosedBackGroundAnimation = colorCode;

			if (value === 1) {
				if (this.visibleArrow1 === 0) {
					this.visibleArrow1 = 1;
				} else if (this.visibleArrow1 === 1) {
					this.visibleArrow1 = 0;
                    this.chosedBackGroundAnimation = "";
				}

				this.visibleArrow2 = 0;
				this.visibleArrow3 = 0;
				this.visibleArrow4 = 0;
				this.visibleArrow5 = 0;
				this.visibleArrow6 = 0;
				this.visibleArrow7 = 0;
				this.visibleArrow8 = 0;
				this.visibleArrow9 = 0;
			} else if (value === 2) {
				if (this.visibleArrow2 === 0) {
					this.visibleArrow2 = 1;
				} else if (this.visibleArrow2 === 1) {
					this.visibleArrow2 = 0;
                    this.chosedBackGroundAnimation = "";
				}

				this.visibleArrow1 = 0;
				this.visibleArrow3 = 0;
				this.visibleArrow4 = 0;
				this.visibleArrow5 = 0;
				this.visibleArrow6 = 0;
				this.visibleArrow7 = 0;
				this.visibleArrow8 = 0;
				this.visibleArrow9 = 0;
			} else if (value === 3) {
				if (this.visibleArrow3 === 0) {
					this.visibleArrow3 = 1;
				} else if (this.visibleArrow3 === 1) {
					this.visibleArrow3 = 0;
                    this.chosedBackGroundAnimation = "";
				}

				this.visibleArrow1 = 0;
				this.visibleArrow2 = 0;
				this.visibleArrow4 = 0;
				this.visibleArrow5 = 0;
				this.visibleArrow6 = 0;
				this.visibleArrow7 = 0;
				this.visibleArrow8 = 0;
				this.visibleArrow9 = 0;
			} else if (value === 4) {
				if (this.visibleArrow4 === 0) {
					this.visibleArrow4 = 1;
				} else if (this.visibleArrow4 === 1) {
					this.visibleArrow4 = 0;
                    this.chosedBackGroundAnimation = "";
				}

				this.visibleArrow1 = 0;
				this.visibleArrow2 = 0;
				this.visibleArrow3 = 0;
				this.visibleArrow5 = 0;
				this.visibleArrow6 = 0;
				this.visibleArrow7 = 0;
				this.visibleArrow8 = 0;
				this.visibleArrow9 = 0;
			} else if (value === 5) {
				if (this.visibleArrow5 === 0) {
					this.visibleArrow5 = 1;
				} else if (this.visibleArrow5 === 1) {
					this.visibleArrow5 = 0;
                    this.chosedBackGroundAnimation = "";
				}

				this.visibleArrow1 = 0;
				this.visibleArrow2 = 0;
				this.visibleArrow3 = 0;
				this.visibleArrow4 = 0;
				this.visibleArrow6 = 0;
				this.visibleArrow7 = 0;
				this.visibleArrow8 = 0;
				this.visibleArrow9 = 0;
			} else if (value === 6) {
				if (this.visibleArrow6 === 0) {
					this.visibleArrow6 = 1;
				} else if (this.visibleArrow6 === 1) {
					this.visibleArrow6 = 0;
                    this.chosedBackGroundAnimation = "";
				}

				this.visibleArrow1 = 0;
				this.visibleArrow2 = 0;
				this.visibleArrow3 = 0;
				this.visibleArrow4 = 0;
				this.visibleArrow5 = 0;
				this.visibleArrow7 = 0;
				this.visibleArrow8 = 0;
				this.visibleArrow9 = 0;
			} else if (value === 7) {
				if (this.visibleArrow7 === 0) {
					this.visibleArrow7 = 1;
				} else if (this.visibleArrow7 === 1) {
					this.visibleArrow7 = 0;
                    this.chosedBackGroundAnimation = "";
				}

				this.visibleArrow1 = 0;
				this.visibleArrow2 = 0;
				this.visibleArrow3 = 0;
				this.visibleArrow4 = 0;
				this.visibleArrow5 = 0;
				this.visibleArrow6 = 0;
				this.visibleArrow8 = 0;
				this.visibleArrow9 = 0;
			} else if (value === 8) {
				if (this.visibleArrow8 === 0) {
					this.visibleArrow8 = 1;
				} else if (this.visibleArrow8 === 1) {
					this.visibleArrow8 = 0;
                    this.chosedBackGroundAnimation = "";
				}

				this.visibleArrow1 = 0;
				this.visibleArrow2 = 0;
				this.visibleArrow3 = 0;
				this.visibleArrow4 = 0;
				this.visibleArrow5 = 0;
				this.visibleArrow6 = 0;
				this.visibleArrow7 = 0;
				this.visibleArrow9 = 0;
			} else if (value === 9) {
				if (this.visibleArrow9 === 0) {
					this.visibleArrow9 = 1;
				} else if (this.visibleArrow9 === 1) {
					this.visibleArrow9 = 0;
                    this.chosedBackGroundAnimation = "";
				}

				this.visibleArrow1 = 0;
				this.visibleArrow2 = 0;
				this.visibleArrow3 = 0;
				this.visibleArrow4 = 0;
				this.visibleArrow5 = 0;
				this.visibleArrow6 = 0;
				this.visibleArrow7 = 0;
				this.visibleArrow8 = 0;
			}
		},
        attachFile: async function(eventf) {
            let self = this;
            var target = eventf.target || window.event.srcElement;
            for (let x = 0; x < target.files.length; x++) {
                let file = target.files[x];
                if (file.type.includes("image")) {
                    self.arrayFileImage.push(file);
                    if (FileReader && file) {
                        var fr = new FileReader();
                        fr.readAsDataURL(file);
                        self.handleFieReader(self, fr, file);
                    }
                }
            }
        },
        handleFieReader(self, fr) {
            fr.onload = function() {
                self.arrayFileReadImage.push(fr.result);
                self.handleEmitFile();
            };
        },
        attachFile1: async function(eventf) {
            let self = this;
            var target = eventf.target || window.event.srcElement;
            for (let x = 0; x < target.files.length; x++) {
                let file = target.files[x];
                if (file.type.includes("video")) {
                    self.arrayFileVideo.push(file);
                    if (FileReader && file) {
                        var fr = new FileReader();
                        fr.readAsDataURL(file);
                        self.handleFieReader1(self, fr, file);
                    }
                }
            }
        },
        handleFieReader1(self, fr) {
            fr.onload = function() {
                self.arrayFileReadVideo.push(fr.result);
                self.handleEmitFile();
            };
        },
        handleEmitFile() {
            this.arrayFile = this.arrayFileImage.concat(this.arrayFileVideo);
            this.arrayFileRead = this.arrayFileReadImage.concat(this.arrayFileReadVideo);
            this.$emit("handleFileUploadImage", this.arrayFile, this.arrayFileRead, "image");
            console.log(this.arrayFile);
            console.log(document.getElementById("embedfileinput").value);
        }
    }
}
</script>
<style>
    [dir] .ql-toolbar.ql-snow + .ql-container.ql-snow {
        height: 100px !important;
        margin-top: 15px;
        border: 1px solid rgba(0, 0, 0, 0.2) !important;
        border-radius: 5px;
        padding-right: 30px;
    }
    [dir] .ql-toolbar.ql-snow {
        display: none;
    }
    .videoListInEditor {
        margin-bottom: 12px;
        object-fit: cover;
        height: 100px;
        min-width: 185px;
    }
    .imageListInEditor {
        height: 90px;
        min-width: 100px;
        object-fit: cover;
        margin-bottom: 12px;
    }
    .moodDropdown {
        display: flex;
        justify-content: flex-end;
        position: relative;
        top: 45px;
        left: 2px;
        margin-bottom: -50px;
        z-index: 1;
    }
    .btnForDropdown {
        border-bottom-width: 0px !important;
    }
    .vs-con-dropdown {
        cursor: pointer;
    }
    .buttonGroupChooseColour {
        width: 40px !important;
        height: 40px !important;
        margin: 0px 5px 0px 5px;
        border-radius: 5px !important;
    }
    .postNowDiv {
        display: flex;
        justify-content: flex-end;
    }
    .addToPostClass {
        display: flex;
        justify-content: flex-end;
        position: absolute;
        margin-top: -6px;
    }
    .imageDescription {
        margin-bottom: auto;
        margin-top: auto;
        word-break: break-all;
        padding-bottom: 10px;
        font-weight: 600;
        margin-left: 5px;
        width: 68%;
    }
    .con-vs-avatar {
        margin: 0px;
    }
</style>