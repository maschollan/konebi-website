<template>
    <div class="grid grid-cols-4 gap-4 p-4 pb-6 mt-3 overflow-y-scroll bg-white rounded-xl">
        <div class="col-span-4 md:col-span-2">
            <div class="text-lg font-medium text-orange-600">Berat :</div>
            <apexchart :options="chartOptions" :series="series" class="md:col-span-3 lg:col-span-6"></apexchart>
        </div>
        <div class="col-span-4 md:col-span-2">
            <div class="text-lg font-medium text-orange-600">Jumlah :</div>
            <apexchart :options="chartOptions" :series="series" class="md:col-span-3 lg:col-span-6"></apexchart>
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
            series: [
                {
                    name: "Udang Jenis 1",
                    data: [31, 40, 28, 51, 42, 67, 90],
                },
                {
                    name: "Udang Jenis 2",
                    data: [11, 32, 45, 32, 34, 52, 41],
                },
                {
                    name: "Udang Jenis 3",
                    data: [16, 9, 21, 18, 29, 36, 32],
                },
            ],
            chartOptions: {
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
                    categories: [
                        "2022-01-19",
                        "2022-02-20",
                        "2022-03-21",
                        "2022-04-22",
                        "2022-05-23",
                        "2022-06-24",
                        "2022-07-25",
                    ],
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
            },
        };
    },
};
</script>
