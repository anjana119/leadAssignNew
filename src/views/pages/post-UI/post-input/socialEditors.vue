<template>
    <vx-card title="Create Post">
        <editor
            @handleInput="handleInput"
            @handleFileUploadImage="handleFileUploadImage"
            @handleLocationControl="handleLocationControl"
        />
    </vx-card>
</template>

<script>
import editor from './editor.vue'
export default {
    components: {
        editor
    },
    data() {
        return {}
    },
    methods: {
        handleInput(con, val) {
            con === "quill" ? this.$emit("handleInput", "quill", val) : this.$emit("handleInput", "color code", val);
        },
        handleFileUploadImage(file, fileReader, condition) {
            this.$emit("handleFileUploadImage", file, fileReader, condition);
        },
        handleLocationControl(center, markers, condition) {
            this.$emit("handleLocationControl", center, markers, condition);
        },
    }
}
</script>
<style>
.vs-dropdown--custom {
    padding: 20px!important;
    padding-top: 12px!important;
}
</style>