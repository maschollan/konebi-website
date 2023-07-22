<template>
    <div class="max-w-full max-h-full" ref="videoContainer">
        <video ref="videoRef" class="video-js vjs-default-skin" controls>
            <source :src="videoSrc" type="video/mp4" />
        </video>
    </div>
</template>

<script>
import videojs from "video.js";
import "video.js/dist/video-js.css";

export default {
    data() {
        return {
            player: null,
        };
    },
    props: {
        videoSrc: {
            type: String,
            required: true,
        },
    },
    mounted() {
        this.player = videojs(this.$refs.videoRef);
        this.player.width(this.$refs.videoContainer.offsetWidth);
        this.player.height(this.$refs.videoContainer.offsetHeight);
        window.addEventListener("resize", this.updateSizePlayer);
    },
    methods: {
        updateSizePlayer() {
            this.player.width(this.$refs.videoContainer.offsetWidth);
            this.player.height(this.$refs.videoContainer.offsetHeight);
        },
    },
    beforeUnmount() {
        if (this.player) {
            this.player.dispose();
        }
        window.removeEventListener("resize", this.updateSizePlayer);
    },
};
</script>

<style>
@import "video.js/dist/video-js.css";
</style>
