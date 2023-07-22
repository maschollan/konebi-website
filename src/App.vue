<template>
    <div class="bg-gradient-to-b from-[#EB997A] to-[#E15E2A] to-47% w-screen h-screen overflow-y-scroll">
        <div class="flex flex-col flex-wrap justify-center max-w-4xl p-4 m-auto lg:max-w-6xl xl:max-w-7xl">
            <div class="flex flex-wrap items-center justify-between">
                <div class="flex flex-wrap items-center justify-center w-full sm:w-1/2 sm:justify-normal">
                    <img src="./assets/logo.png" alt="logo" class="w-[7rem] h-[7rem]" />
                    <div
                        class="text-lg font-semibold text-right text-white sm:text-left whitespace-nowrap ms-auto sm:ms-3"
                    >
                        <p>Monitoring</p>
                        <p>Kontrol</p>
                        <p>Laporan</p>
                    </div>
                </div>

                <div class="flex justify-center w-full sm:justify-end sm:w-1/2">
                    <div class="relative flex flex-wrap justify-center p-1 bg-white rounded-full h-min">
                        <div
                            class="flex items-center justify-center w-20 h-10 transition rounded-full cursor-pointer"
                            @click="tab = 'home'"
                            :class="{ 'bg-orange-400': tab == 'home', 'hover:bg-orange-100': tab != 'home' }"
                        >
                            <svg
                                xmlns="http://www.w3.org/2000/svg"
                                class="w-6 h-"
                                :class="{ 'fill-orange-400': tab != 'home', 'fill-white': tab == 'home' }"
                                height="48"
                                viewBox="0 -960 960 960"
                                width="48"
                            >
                                <path
                                    d="M220-120q-24.75 0-42.375-17.625T160-180v-390q0-14.25 6.375-27T184-618l260-195q8.295-6 17.344-9 9.049-3 18.853-3 9.803 0 18.717 3 8.915 3 17.086 9l260 195q11.25 8.25 17.625 21T800-570v390q0 24.75-17.625 42.375T740-120H560v-280H400v280H220Z"
                                />
                            </svg>
                        </div>
                        <div
                            class="flex items-center justify-center w-20 h-10 transition rounded-full cursor-pointer"
                            @click="tab = 'laporan'"
                            :class="{ 'bg-orange-400': tab == 'laporan', 'hover:bg-orange-100': tab != 'laporan' }"
                        >
                            <svg
                                xmlns="http://www.w3.org/2000/svg"
                                class="w-6 h-6"
                                :class="{ 'fill-orange-400': tab != 'laporan', 'fill-white': tab == 'laporan' }"
                                height="48"
                                viewBox="0 -960 960 960"
                                width="48"
                            >
                                <path
                                    d="M314.175-277q12.825 0 21.325-8.625T344-307v-215q0-12.75-8.675-21.375-8.676-8.625-21.5-8.625-12.825 0-21.325 8.625T284-522v215q0 12.75 8.675 21.375 8.676 8.625 21.5 8.625Zm166 0q12.825 0 21.325-8.625T510-307v-346q0-12.75-8.675-21.375-8.676-8.625-21.5-8.625-12.825 0-21.325 8.625T450-653v346q0 12.75 8.675 21.375 8.676 8.625 21.5 8.625Zm166 0q12.825 0 21.325-8.625T676-307v-88q0-12.75-8.675-21.375-8.676-8.625-21.5-8.625-12.825 0-21.325 8.625T616-395v88q0 12.75 8.675 21.375 8.676 8.625 21.5 8.625ZM180-120q-24 0-42-18t-18-42v-600q0-24 18-42t42-18h600q24 0 42 18t18 42v600q0 24-18 42t-42 18H180Z"
                                />
                            </svg>
                        </div>
                        <div
                            class="flex items-center justify-center w-20 h-10 text-white transition rounded-full cursor-pointer"
                            @click="tab = 'setting'"
                            :class="{ 'bg-orange-400': tab == 'setting', 'hover:bg-orange-100': tab != 'setting' }"
                        >
                            <svg
                                xmlns="http://www.w3.org/2000/svg"
                                class="w-6 h-6"
                                :class="{ 'fill-orange-400': tab != 'setting', 'fill-white': tab == 'setting' }"
                                height="48"
                                viewBox="0 -960 960 960"
                                width="48"
                            >
                                <path
                                    d="M546-80H414q-11 0-19.5-7T384-105l-16-101q-19-7-40-19t-37-25l-93 43q-11 5-22 1.5T159-220L93-337q-6-10-3-21t12-18l86-63q-2-9-2.5-20.5T185-480q0-9 .5-20.5T188-521l-86-63q-9-7-12-18t3-21l66-117q6-11 17-14.5t22 1.5l93 43q16-13 37-25t40-18l16-102q2-11 10.5-18t19.5-7h132q11 0 19.5 7t10.5 18l16 101q19 7 40.5 18.5T669-710l93-43q11-5 22-1.5t17 14.5l66 116q6 10 3.5 21.5T858-584l-86 61q2 10 2.5 21.5t.5 21.5q0 10-.5 21t-2.5 21l86 62q9 7 12 18t-3 21l-66 117q-6 11-17 14.5t-22-1.5l-93-43q-16 13-36.5 25.5T592-206l-16 101q-2 11-10.5 18T546-80Zm-66-270q54 0 92-38t38-92q0-54-38-92t-92-38q-54 0-92 38t-38 92q0 54 38 92t92 38Z"
                                />
                            </svg>
                        </div>
                        <div
                            class="flex items-center justify-center w-20 h-10 text-white transition rounded-full cursor-pointer hover:bg-orange-100"
                        >
                            <svg
                                xmlns="http://www.w3.org/2000/svg"
                                class="w-6 h-6 fill-orange-400"
                                height="48"
                                viewBox="0 -960 960 960"
                                width="48"
                            >
                                <path
                                    d="M180-120q-24 0-42-18t-18-42v-600q0-24 18-42t42-18h478q12.444 0 23.722 5T701-822l121 121q8 8 13 19.278 5 11.278 5 23.722v478q0 24-18 42t-42 18H180Zm299.765-125Q523-245 553.5-275.265q30.5-30.264 30.5-73.5Q584-392 553.735-422.5q-30.264-30.5-73.5-30.5Q437-453 406.5-422.735q-30.5 30.264-30.5 73.5Q376-306 406.265-275.5q30.264 30.5 73.5 30.5ZM263-584h298q12.75 0 21.375-8.625T591-614v-83q0-12.75-8.625-21.375T561-727H263q-12.75 0-21.375 8.625T233-697v83q0 12.75 8.625 21.375T263-584Z"
                                />
                            </svg>
                        </div>
                    </div>
                </div>
            </div>

            <home-page v-show="tab == 'home'" />
            <laporan-page v-show="tab == 'laporan'" />
            <setting-page v-show="tab == 'setting'" />

            <div class="mt-4 font-semibold text-center text-white">Copyright © {{ year }} Godbless Team</div>
        </div>
    </div>
</template>

<script>
import HomePage from "./components/HomePage.vue";
import LaporanPage from "./components/LaporanPage.vue";
import SettingPage from "./components/SettingPage.vue";

export default {
    name: "App",
    components: {
        HomePage,
        LaporanPage,
        SettingPage,
    },
    data() {
        return {
            year: new Date().getFullYear(),
            tab: "home",
        };
    },
    methods: {
        randomNumber(min, max) {
            return Math.floor(Math.random() * (max - min + 1) + min);
        },
    },
    mounted() {},
    computed: {},
};
</script>

<style scoped></style>
