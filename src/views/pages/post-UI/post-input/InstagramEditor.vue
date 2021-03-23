<template>
    <div>
        <h5>Placements</h5>
        <ul class="faq-supporters mt-4" style="max-height: 225px; overflow: auto;">
            <li v-for="listItem in list" :key="listItem.email" class="mt-4">
                <div class="flex items-center">
                    <vs-checkbox v-model="checkBox1" :vs-value="listItem.name" />
                    <vs-avatar class="mr-3" :src="listItem.src" size="35px" />
                    <div class="leading-tight">
                        <p class="font-semibold">
                            {{ listItem.name }}
                            <vs-avatar
                                style="position: relative; top: 10px;"
                                :src="listItem.type === 'page' ? 'https://i.pinimg.com/originals/4a/f0/c7/4af0c7a139b4a6199d7fb78c207629fa.png' : 'https://img.favpng.com/18/5/20/blue-human-behavior-silhouette-area-communication-png-favpng-wLT3QYknSwc68uu9GAUHGS5FY_t.jpg'"
                                size="20px"
                            />
                        </p>
                        <small>{{ listItem.email }}</small>
                    </div>
                </div>
                <vs-divider />
            </li>
        </ul>
        <div class="mt-5 uploadImagesInsta">
            <div style="padding: 20px;">
                <vs-input type="file" multiple id="embedfileinput" @change="attachFile" style="display: none;" />
                <div @click="handleFileUploadControl">
                    Upload
                </div>
            </div>
        </div>
        <div class="mt-5 postNowDiv">
            <vs-button color="primary" type="filled" icon-pack="feather" icon="icon-check">Post Now</vs-button>
        </div>
    </div>
</template>

<script>
export default {
    components: {},
    data() {
        return {
            badge1: "",
            list: [
                {
                    name: "Pet Lab Co.",
                    src: "https://www.fluentu.com/blog/chinese/wp-content/uploads/2016/05/learn-chinese-facebook-5.png",
                    email: "zackary@mockus.com",
                    type: "group"
                },
                {
                    name: "Julie's Freebies",
                    src: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTj4xVR7Mg2MHyCeMNhkp62gt4xtgZsYOEx-g&usqp=CAU",
                    email: "rosemarie@fifield.com",
                    type: "group"
                },
                {
                    name: "Stephan Speaks Relations",
                    src: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRT9Pcb3VwHw5FYiKx05AeQPcVufBzId--G5Q&usqp=CAU",
                    email: "bernard@laboy.com",
                    type: "group"
                },
                {
                    name: "Inner Light Media",
                    src: "https://www.hackingchinese.com/wp-content/uploads/2012/08/yong.png",
                    email: "sue@haakinson.com",
                    type: "page"
                },
                {
                    name: "ADT",
                    src: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR5FoWABvPuShdttvMU2lKHBFY9u6Pxc0l1eQ&usqp=CAU",
                    email: "valerie@pou.com",
                    type: "group"
                },
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
                    type: "page"
                },
                {
                    name: "Nikon Instruments",
                    src: "https://pbs.twimg.com/profile_images/576147198812905473/7PVBhjL9_400x400.png",
                    email: "billie@tinnes.com",
                    type: "page"
                }
            ],
            image: null,
            arrayFile: [],
            arrayFileRead: []
        }
    },
    watch: {},
    mounted() {},
    methods: {
        handleFileUploadControl() {
            document.getElementById("embedfileinput").click();
        },
        attachFile: async function(eventf) {
            let self = this;
            var target = eventf.target || window.event.srcElement;
            for (let x = 0; x < target.files.length; x++) {
                let file = target.files[x];
                self.arrayFile.push(file);
                if (FileReader && file) {
                    var fr = new FileReader();
                    fr.readAsDataURL(file);
                    self.handleFieReader(self, fr, file);
                }
            }
        },
        handleFieReader(self, fr, file) {
            fr.onload = function() {
                self.arrayFileRead.push(fr.result);
                self.handleEmitFile(file, fr.result);
            };
        },
        handleEmitFile() {
            this.$emit("handleFileUploadImage", this.arrayFile, this.arrayFileRead, "image");
        }
    }
}
</script>
<style>
    .uploadImagesInsta {
        display: flex;
        justify-content: center;
        border: 1px solid rgba(0, 0, 0, 0.2) !important;
        width: 20%;
        border-radius: 5px;
        margin-left: auto;
        margin-right: auto;
        cursor: pointer;
        font-weight: 600;
        border-style: dashed !important;
    }
    .uploadImagesInsta:hover {
        background: whitesmoke;
        font-weight: 700;
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
</style>