<template>
    <div class="grid grid-cols-6 gap-4 py-5 mt-5 overflow-y-scroll">
        <div class="flex items-center col-span-2">
            <div
                class="text-lg font-medium w-[100px] h-[100px] border-[2px] border-white p-4 rounded-full group cursor-pointer"
                :class="{
                    'bg-green-500 hover:bg-green-600 border-white': powerKonveyor,
                    'border-gray-600 bg-gray-400 hover:bg-gray-300': !powerKonveyor,
                }"
                @click="powerKonveyor = !powerKonveyor"
            >
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    height="48"
                    viewBox="0 -960 960 960"
                    width="48"
                    class="w-full h-full"
                    :class="{ 'fill-white': powerKonveyor, 'fill-gray-600': !powerKonveyor }"
                >
                    <path
                        d="M479.825-438Q467-438 458.5-446.625T450-468v-346q0-12.75 8.675-21.375 8.676-8.625 21.5-8.625 12.825 0 21.325 8.625T510-814v346q0 12.75-8.675 21.375-8.676 8.625-21.5 8.625ZM480-118q-75 0-140.5-28.5t-114-77q-48.5-48.5-77-114T120-478q0-71 28-135.5T226-729q9-9 22.5-9.5T271-730q9 9 7.5 21.5T268-687q-42 42-65 95.5T180-478q0 125.357 87.321 212.679Q354.643-178 480-178t212.679-87.321Q780-352.643 780-478q0-60-22.644-113.804Q734.712-645.609 693-688q-9-9-10-21.5t8-20.5q10-10 23.5-8.5T738-727q49 51 75.5 114.969Q840-548.062 840-478q0 75-28.5 140.5t-77 114q-48.5 48.5-114 77T480-118Z"
                    />
                </svg>
            </div>
            <div class="text-white ms-4">
                <div class="text-lg font-semibold">Power Konveyor</div>
                <div class="text-4xl font-bold">{{ powerKonveyor ? "ON" : "OFF" }}</div>
            </div>
        </div>
        <div class="flex items-center col-span-2">
            <div
                class="text-lg font-medium w-[100px] h-[100px] border-[2px] border-white p-4 rounded-full group cursor-pointer"
                :class="{
                    'bg-green-500 hover:bg-green-600 border-white': powerPompa,
                    'border-gray-600 bg-gray-400 hover:bg-gray-300': !powerPompa,
                }"
                @click="powerPompa = !powerPompa"
            >
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    height="48"
                    viewBox="0 -960 960 960"
                    width="48"
                    class="w-full h-full"
                    :class="{ 'fill-white': powerPompa, 'fill-gray-600': !powerPompa }"
                >
                    <path
                        d="M479.825-438Q467-438 458.5-446.625T450-468v-346q0-12.75 8.675-21.375 8.676-8.625 21.5-8.625 12.825 0 21.325 8.625T510-814v346q0 12.75-8.675 21.375-8.676 8.625-21.5 8.625ZM480-118q-75 0-140.5-28.5t-114-77q-48.5-48.5-77-114T120-478q0-71 28-135.5T226-729q9-9 22.5-9.5T271-730q9 9 7.5 21.5T268-687q-42 42-65 95.5T180-478q0 125.357 87.321 212.679Q354.643-178 480-178t212.679-87.321Q780-352.643 780-478q0-60-22.644-113.804Q734.712-645.609 693-688q-9-9-10-21.5t8-20.5q10-10 23.5-8.5T738-727q49 51 75.5 114.969Q840-548.062 840-478q0 75-28.5 140.5t-77 114q-48.5 48.5-114 77T480-118Z"
                    />
                </svg>
            </div>
            <div class="text-white ms-4">
                <div class="text-lg font-semibold">Power Pompa</div>
                <div class="text-4xl font-bold">{{ powerPompa ? "ON" : "OFF" }}</div>
            </div>
        </div>
        <div class="flex flex-col col-span-2 text-white">
            <div class="text-lg font-semibold">Speed Konveyor</div>
            <div class="mb-5 text-4xl font-bold">{{ speed }}</div>
            
        </div>
    </div>
</template>

<script>
export default {
    name: "SettingPage",
    data() {
        return {
            speed: 50,
            powerKonveyor: true,
            powerPompa: false,
        };
    },
    methods: {},
};
</script>
