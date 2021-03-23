<template>
    <div>

        <!-- Create post -->
        <vs-row vs-w="12">
            <vs-col style="padding-right: 10px;" vs-type="flex" vs-justify="center" vs-align="center" vs-lg="6" vs-md="6" vs-sm="12" vs-xs="12">
                <vx-card
                    title="Create"
                    title-color="primary"
                >
                    <div>
                        <vs-avatar class="m-0" src="/img/avatar-s-5.99691e54.jpg" size="55px" />
                        <span class="userName">
                            Adam Afreda 
                        </span>
                        <vs-button color="primary" type="filled" icon-pack="feather" icon="icon-users" class="selectFriendsBtn">Friends</vs-button>
                    </div>
                    <hr style="margin-top: -25px; margin-bottom: 40px;" />
                    <vs-row vs-w="12" class="rowForTreeView">
                        <vs-col vs-type="flex" vs-justify="center" vs-align="center" vs-lg="6" vs-md="6" vs-sm="12" vs-xs="12">
                            <treeselect
                                :multiple="true"
                                :clearable="true"
                                :searchable="false"
                                :disabled="false"
                                :open-on-click="true"
                                :open-on-focus="false"
                                :clear-on-select="true"
                                :close-on-select="false"
                                :always-open="false"
                                :append-to-body="false"
                                :options="options"
                                :limit="2"
                                :max-height="300"
                                v-model="socialMedias"
                                ref="secondTreeSelect"
                                placeholder="Select Social Media To Share Post"
                            />
                        </vs-col>
                        <vs-col style="" vs-type="flex" vs-justify="center" vs-align="center" vs-lg="6" vs-md="6" vs-sm="12" vs-xs="12">
                            <div style="display: flex; justify-content: flex-end;">
                                <vs-button
                                    type="relief"
                                    class="tagBtn"
                                    icon-pack="feather"
                                    icon="icon-check"
                                    v-for="(item, index) in activeBtnArray"
                                    :key="index"
                                    @click="handlePreview(item)"
                                >
                                    {{item}}
                                </vs-button>
                            </div>
                        </vs-col>
                    </vs-row>
                    <quill-editor v-model="postData.content" ref="quillEditorRef" />
                    <hr style="margin-top: 14px; margin-bottom: 20px;" />
                    <div class="flex flex-wrap" v-if="socialMediaText === 'Face Book'">
                        <div class="btn-group">
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
                    <vs-row vs-w="12" style="border: 1px solid #e4e4e4; border-radius: 5px; padding: 10px; margin-top: 20px;">
                        <vs-col vs-type="flex" vs-align="center" vs-lg="9" vs-md="9" vs-sm="9" vs-xs="9">
                            <span style="font-weight: bold; font-size: 16px;">
                                Add to Your Post
                            </span>
                        </vs-col>
                        <vs-col vs-type="flex" vs-justify="center" vs-align="center" vs-lg="1" vs-md="1" vs-sm="1" vs-xs="1">
                            <vx-tooltip text="Add Image" position="bottom">
                                <vs-button color="primary" type="flat" icon-pack="feather" icon="icon-camera" />
                            </vx-tooltip>
                        </vs-col>
                        <vs-col vs-type="flex" vs-justify="center" vs-align="center" vs-lg="1" vs-md="1" vs-sm="1" vs-xs="1">
                            <vx-tooltip text="Add Video" position="bottom">
                                <vs-button color="primary" type="flat" icon-pack="feather" icon="icon-camera" />
                            </vx-tooltip>
                        </vs-col>
                        <vs-col vs-type="flex" vs-justify="center" vs-align="center" vs-lg="1" vs-md="1" vs-sm="1" vs-xs="1">
                            <vx-tooltip text="Add Location" position="bottom">
                                <vs-button color="primary" type="flat" icon-pack="feather" icon="icon-camera" />
                            </vx-tooltip>
                        </vs-col>
                    </vs-row>
                    <div style="display: flex; justify-content: center;">
                        <vs-button color="primary" type="filled" icon-pack="feather" icon="icon-check" style="padding: 10px !important; margin-top: 10px;">Post Now</vs-button>
                    </div>
                </vx-card>
            </vs-col>

            <!-- FaceBook, twitter view -->
            <vs-col vs-type="flex" vs-justify="center" vs-align="center" vs-lg="6" vs-md="6" vs-sm="12" vs-xs="12">
                <vx-card
                    :title="socialMediaText === '' ? 'Preview' : 'Preview - ' + socialMediaText"
                    title-color="primary"
                    :style="socialMediaText === 'Face Book' ? 'height: 758px;' : 'height: 700px;'"
                >
                    <div>
                        <vs-avatar class="m-0" src="/img/avatar-s-5.99691e54.jpg" size="55px" />
                        <span class="userName">
                            Adam Afreda 
                        </span>
                        <span class="dateFormateInPreview">
                            {{ postData.date }}
                        </span>
                    </div>
                    <hr style="margin-top: 14px; margin-bottom: 20px;" />
                    <div
                        :style="socialMediaText === 'Face Book' ? postData.chosedBackGroundAnimation : socialMediaText === 'Twitter' ? 'background: #f9f9f9;' : 'background: none;'"
                        style="padding: 20px; border-radius: 8px; max-height: 300px; overflow: auto;" v-html="postData.content"
                    />
                    <vs-row vs-w="12" class="facebookBottomClass" :style="socialMediaText === 'Face Book' ? 'top: 640px;' : 'top: 585px;'">
                        <vs-col
                            v-show="socialMediaText === 'Face Book'"
                            vs-type="flex"
                            vs-justify="center"
                            vs-align="center"
                            vs-lg="4"
                            vs-md="4"
                            vs-sm="4"
                            vs-xs="4"
                            v-for="(item, index) in previewFooterSection.faceBook"
                            :key="index"
                        >
                            <vs-button style="padding: 10px 60px 10px 60px;" color="primary" type="flat" icon-pack="feather" :icon="item.icon">
                                {{item.text}}
                            </vs-button>
                        </vs-col>
                        <vs-col
                            v-show="socialMediaText === 'Twitter'"
                            vs-type="flex"
                            vs-justify="center"
                            vs-align="center"
                            vs-lg="3"
                            vs-md="3"
                            vs-sm="3"
                            vs-xs="3"
                            v-for="(item, index) in previewFooterSection.twitter"
                            :key="index"
                        >
                            <vs-button style="padding: 10px 60px 10px 60px;" color="primary" type="flat" icon-pack="feather" :icon="item.icon">
                                {{item.text}}
                            </vs-button>
                        </vs-col>
                    </vs-row>
                </vx-card>
            </vs-col>
        </vs-row>
    </div>
</template>

<!-- include Vue 2.x -->
<script src="https://cdn.jsdelivr.net/npm/vue@^2"></script>

<!-- include vue-treeselect & its styles -->
<script src="https://cdn.jsdelivr.net/npm/@riophae/vue-treeselect@^0.4.0/dist/vue-treeselect.umd.min.js"></script>

<script>
// import the component
import Treeselect from '@riophae/vue-treeselect'

// import the styles
import '@riophae/vue-treeselect/dist/vue-treeselect.css'

import 'quill/dist/quill.core.css'
import 'quill/dist/quill.snow.css'
import 'quill/dist/quill.bubble.css'

import { quillEditor } from 'vue-quill-editor'

export default {
    components: {
        quillEditor,
        Treeselect
    },
    data() {
        return {
            postData: {
                date:  "March 3, 2021",
                content: "" ,
                chosedBackGroundAnimation: ""
            },
            previewFooterSection: {
                faceBook: [
                    {
                        text: "Like",
                        icon: "icon-check"
                    },
                    {
                        text: "Comment",
                        icon: "icon-check"
                    },
                    {
                        text: "Share",
                        icon: "icon-check"
                    }
                ],
                twitter: [
                    {
                        text: "Reply",
                        icon: "icon-check"
                    },
                    {
                        text: "Retweet",
                        icon: "icon-check"
                    },
                    {
                        text: "Like",
                        icon: "icon-check"
                    },
                    {
                        text: "Share",
                        icon: "icon-check"
                    }
                ]
            },
            socialMediaText: "",
            socialMedias: [],
            activeBtnArray: [],
            multiple: true,
            value: null,
            options: [
                {
                    id: "Face Book",
                    label: "Face Book"
                },
                {
                    id: "Twitter",
                    label: "Twitter"
                },
                {
                    id: "Instagram",
                    label: "Instagram",
                    isDisabled: true
                },
                {
                    id: "LinkedIn",
                    label: "LinkedIn",
                    isDisabled: true
                },
                {
                    id: "You Tube",
                    label: "You Tube",
                    isDisabled: true
                }
            ],
            schowComp: 0,
			visibleArrow1: 0,
			visibleArrow2: 0,
			visibleArrow3: 0,
			visibleArrow4: 0,
			visibleArrow5: 0,
			visibleArrow6: 0,
			visibleArrow7: 0,
			visibleArrow8: 0,
			visibleArrow9: 0
        }
    },
    watch: {
        socialMedias() {
            this.activeBtnArray = this.socialMedias;
            if (this.socialMedias.length === 1) {
                this.socialMediaText = this.socialMedias[0];
            } else if (this.socialMedias.length === 0) {
                this.socialMediaText = "";
            }
        }
    },
    mounted() {
        this.focusTreeSelect();
        this.focusQuillEditor();
    },
    methods: {
        focusTreeSelect() {
            this.$refs.secondTreeSelect.$el.children[0].style.height = '48px';
            this.$refs.secondTreeSelect.$el.children[1].style.fontWeight = "600";
            this.$refs.secondTreeSelect.$el.children[1].style.fontSize = '13px';
            this.$refs.secondTreeSelect.$el.children[0].style.borderRadius = '2px';
            this.$refs.secondTreeSelect.$el.children[0].children[0].children[0].children[0].style.top = '7px';
        },
        focusQuillEditor() {
            this.$refs.quillEditorRef.$el.children[1].firstChild.dataset.placeholder = "Enter You Content ..."
        },
        handlePreview(text) {
            this.socialMediaText = text;
        },
        handleCheck(value, colorCode) {
			this.postData.chosedBackGroundAnimation = colorCode;

			if (value === 1) {
				if (this.visibleArrow1 === 0) {
					this.visibleArrow1 = 1;
				} else if (this.visibleArrow1 === 1) {
					this.visibleArrow1 = 0;
                    this.postData.chosedBackGroundAnimation = "";
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
                    this.postData.chosedBackGroundAnimation = "";
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
                    this.postData.chosedBackGroundAnimation = "";
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
                    this.postData.chosedBackGroundAnimation = "";
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
                    this.postData.chosedBackGroundAnimation = "";
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
                    this.postData.chosedBackGroundAnimation = "";
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
                    this.postData.chosedBackGroundAnimation = "";
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
                    this.postData.chosedBackGroundAnimation = "";
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
                    this.postData.chosedBackGroundAnimation = "";
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
		}
    }
}
</script>

<style>
.treeSelectParent {
    width: 50%;
    float: right;
    position: relative;
    bottom: 45px;
}
.userName {
    font-size: 18px;
    font-weight: 600;
    font-family: ui-sans-serif;
    position: relative;
    bottom: 42px;
    left: 15px;
}
.selectFriendsBtn {
    padding: 5px 15px 5px 15px;
    position: relative;
    bottom: 45px;
    left: 70px;
    font-weight: 600;
}
.dateFormateInPreview {
    position: relative;
    bottom: 15px;
    font-size: 12px;
    right: 95px;
}
.tagBtn {
    padding: 6px;
    font-size: 10px;
    padding: 6px !important;
    margin-right: 4px;
    position: relative;
}
/* [dir] .ql-toolbar.ql-snow + .ql-container.ql-snow {
    height: 300px !important;
    border: none;
}
[dir] .ql-toolbar.ql-snow {
    display: none;
} */
.rowForTreeView {
    position: relative;
    bottom: 20px;
}
.buttonGroupChooseRight {
    width: 40px;
    height: 40px;
    border-radius: 5px !important;
}
.buttonGroupChooseLeft {
    margin-right: 5px;
    width: 40px;
    height: 40px;
    border-radius: 5px !important;
}
.buttonGroupChooseColour {
    width: 40px !important;
    height: 40px !important;
    margin: 0px 5px 0px 5px;
    border-radius: 5px !important;
}
.facebookBottomClass {
    border-top: 1px solid #969696;
    padding: 15px;
    margin-left: -21px;
    position: absolute;
}
</style>
