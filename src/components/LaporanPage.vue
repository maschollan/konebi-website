<template>
    <div class="grid grid-cols-4 gap-4 p-4 pb-6 mt-3 overflow-y-scroll bg-white rounded-xl">
        <div class="col-span-4 md:col-span-2">
            <div class="text-lg font-medium text-orange-600" @click="log">Berat :</div>
            <apexchart :options="chartOptions" :series="series_berat" class="md:col-span-3 lg:col-span-6"></apexchart>
        </div>
        <div class="col-span-4 md:col-span-2">
            <div class="text-lg font-medium text-orange-600">Jumlah :</div>
            <apexchart :options="chartOptions" :series="series_jumlah" class="md:col-span-3 lg:col-span-6"></apexchart>
        </div>
    </div>
</template>

<script>
import VueApexCharts from "vue3-apexcharts";

export default {
    name: "LaporanPage",
    components: {
        apexchart: VueApexCharts,
    },
    data() {
        return {
        };
    },
    props: {
        laporans: {
            type: Array,
            required: true,
        },
    },
    computed: {
        transformdata() {
            const combinedData = {};

            this.laporans.map((item) => {
                const beratValues = item.berat.split("|").map((val) => parseInt(val));
                const jumlahValues = item.jumlah.split("|").map((val) => parseInt(val));

                const date = item.created_at.split("T")[0];

                if (!combinedData[date]) {
                    combinedData[date] = {
                        berat: [beratValues],
                        jumlah: [jumlahValues],
                    };
                } else {
                    combinedData[date].berat.push(beratValues);
                    combinedData[date].jumlah.push(jumlahValues);
                }
            });

            const summarizedData = Object.keys(combinedData).map((date) => {
                const beratSum = Array(3).fill(0);
                const jumlahSum = Array(3).fill(0);

                combinedData[date].berat.forEach((beratValues) => {
                    beratValues.forEach((val, index) => {
                        beratSum[index] += val;
                    });
                });

                combinedData[date].jumlah.forEach((jumlahValues) => {
                    jumlahValues.forEach((val, index) => {
                        jumlahSum[index] += val;
                    });
                });

                return {
                    created_at: date,
                    berat: beratSum.join("|"),
                    jumlah: jumlahSum.join("|"),
                };
            });

            return summarizedData;
        },

        berat() {
            const arr = this.transformdata.map((laporan) => laporan.berat.split("|"));
            if (arr.length > 0) return arr[0].map((col, i) => arr.map((row) => row[i]));
            return [[], [], []];
        },
        jumlah() {
            const arr = this.transformdata.map((laporan) => laporan.jumlah.split("|"));
            if (arr.length > 0) return arr[0].map((col, i) => arr.map((row) => row[i]));
            return [[], [], []];
        },
        created_at() {
            return this.transformdata.map((laporan) => laporan.created_at);
        },
        chartOptions() {
            return {
                chart: {
                    type: "bar",
                },
                dataLabels: {
                    enabled: false,
                },
                stroke: {
                    curve: "smooth",
                },
                xaxis: {
                    type: "datetime",
                    categories: this.created_at,
                },
                legend: {
                    position: "right",
                    offsetY: 40,
                },
                tooltip: {
                    x: {
                        format: "dd MMMM yyyy",
                    },
                },
            };
        },
        series_berat() {
            return this.berat.map((item, index) => {
                return {
                    name: `Udang Jenis ${index + 1}`,
                    data: item,
                };
            });
        },
        series_jumlah() {
            return this.jumlah.map((item, index) => {
                return {
                    name: `Udang Jenis ${index + 1}`,
                    data: item,
                };
            });
        },
    },
    mounted() {},
    methods: {
        log() {
            console.log(this.laporans);
            console.log(this.transformdata);
            console.log(this.jumlah);
            console.log(this.berat);
        },
    },
};
</script>
