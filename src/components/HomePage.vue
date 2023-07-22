<template>
    <div class="grid grid-cols-6 gap-4 p-4 pb-6 mt-3 overflow-y-scroll bg-white rounded-xl">
        <div class="col-span-3 md:col-span-2">
            <div class="text-lg font-medium text-orange-600">Berat :</div>
            <div class="h-[96px] bg-cyan-200 mt-4 rounded-xl p-3 flex flex-col justify-between" v-for="i in 3" :key="i">
                <div class="text-sm text-cyan-800">Udang Jenis {{ i }}</div>
                <div class="flex items-end justify-between mt-auto">
                    <div class="text-3xl font-bold text-cyan-800">{{ randomNumber(100, 999) }}</div>
                    <div class="text-2xl font-semibold text-cyan-800">gram</div>
                </div>
            </div>
        </div>
        <div class="col-span-3 md:col-span-2">
            <div class="text-lg font-medium text-orange-600">Jumlah :</div>
            <div class="h-[96px] bg-cyan-200 mt-4 rounded-xl p-3 flex flex-col justify-between" v-for="i in 3" :key="i">
                <div class="text-sm text-cyan-800">Udang Jenis {{ i }}</div>
                <div class="flex items-end justify-between mt-auto">
                    <div class="text-3xl font-bold text-cyan-800">{{ randomNumber(100, 999) }}</div>
                    <div class="text-2xl font-semibold text-cyan-800">ekor</div>
                </div>
            </div>
        </div>
        <div class="col-span-6 md:col-span-2">
            <div class="text-lg font-medium text-orange-600">Live Kamera :</div>
            <video-player videoSrc="http://vjs.zencdn.net/v/oceans.mp4" class="mt-3 overflow-hidden rounded-xl" />
        </div>
    </div>
</template>

<script>
import VideoPlayer from "./VideoPlayer.vue";

export default {
    components: {
        VideoPlayer,
    },
    methods: {
        randomNumber(min, max) {
            return Math.floor(Math.random() * (max - min + 1) + min);
        },
    },
};
</script>
