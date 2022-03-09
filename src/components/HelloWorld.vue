<template>
 <div class="pt-4 bg-slate-200">
    <div class="grid-rows-3 flex">
    <div class=" flex-none w-80"></div>
    <div class="bg-slate-100 grow p-5">
      <div class="grid grid-cols-4 items-center">
        <img
          class="h-10 w-10"
          src="https://tailwindui.com/img/logos/workflow-mark-indigo-600.svg"
          alt=""
        />
        <div class="flex flex-col text-center col-span-2">
          <p class="text-base font-medium">INTEGRATED COMMAND CENTER</p>
          <p class="text-base font-medium text-gray-500">
            PERUMDA TIRTA SAIL CRUISE PINK BEACH KOMODO
          </p>
        </div>
        <div></div>
      </div>
    </div>
    <div class=" flex-none w-80 p-4">
      <div class="flex  mt-3">
        <img
          class="inline-block h-10 w-10 rounded-full ring-2 ring-white"
          src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
          alt=""
        />
        <div class="flex flex-col ml-2">
          <p class="text-sm font-medium">Direktur</p>
          <p class="text-sm font-medium text-gray-500">Moch Anji Sumarn..</p>
        </div>
      </div>
    </div>
  </div>

  <!-- Body -->
  <div class="grid-rows-3 flex bg-slate-200">
    <div class="flex-none w-80 pl-2">
      <div
        class="
          relative
          block
          p-4
          border border-gray-100
          rounded-xl
          mx-4
          bg-white
          my-4
        "
      >
        <div class="flex justify-between">
          <p class="text-xs font-light">Profit Bersih</p>
          <p class="text-xs font-normal">2%</p>
        </div>
        <p class="font-medium text-3xl">Rp250 Jt</p>
        <hr class="my-2" />
        <div class="flex justify-between items-center">
          <p class="text-xs font-light">Pendapatan</p>
          <p class="text-base font-medium">Rp1,5M</p>
        </div>
      </div>

      <div
        class="
          relative
          block
          p-4
          border border-gray-100
          rounded-xl
          mx-4
          bg-white
          my-4
        "
      >
        <div class="flex justify-between">
          <p class="text-xs font-light">Profit Bersih</p>
          <XIcon class="h-4 w-4" />
        </div>
        <div class="flex justify-between items-center">
          <p class="font-medium text-3xl my-3">82%</p>
          <p class="text-xs font-medium mr-3">18%</p>
        </div>
      </div>

      <div
        class="
          relative
          block
          p-4
          border border-gray-100
          rounded-xl
          mx-4
          bg-white
          my-4
        "
      >
        <div class="flex justify-between">
          <p class="text-xs font-light">Jumlah Pelanggan</p>
          <p class="text-xs font-normal">10%</p>
        </div>
        <p class="font-medium text-2xl">2.050</p>
        <hr class="my-2" />
        <div class="grid grid-cols-2 items-center gap-2">
          <div class="flex flex-row place-items-center justify-between">
            <p class="text-xs font-light">Jumlah SR</p>
            <p class="text-base font-medium">2000</p>
          </div>
          <div class="flex flex-row place-items-center justify-between">
            <p class="text-xs font-light mr-1">Jumlah MBR</p>
            <p class="text-base font-medium">50</p>
          </div>
        </div>
      </div>

      <div
        class="
          relative
          block
          p-4
          border border-gray-100
          rounded-xl
          mx-4
          bg-white
          my-4
        "
      >
        <div class="flex justify-between">
          <p class="text-xs font-light">Pengaduan</p>
          <XIcon class="h-4 w-4" />
        </div>
        <div class="flex justify-between items-center">
          <p class="font-medium text-3xl my-3">50%</p>
          <p class="text-xs font-medium mr-3">90%</p>
        </div>
        <p class="text-xs">
          Penyelesaian Pengaduan <span class="font-semibold">90.54%</span>
        </p>
      </div>

      <div
        class="
          relative
          block
          p-4
          border border-gray-100
          rounded-xl
          mx-4
          bg-white
          my-4
        "
      >
        <div class="flex justify-between">
          <p class="text-xs font-light">Tingkat Penyelesaian Pengaduan</p>
          <XIcon class="h-4 w-4" />
        </div>
        <div class="grid grid-cols-2">
          <PieChart :chartData="testData" :options="options" class="mr-2" />
          <div class="flex flex-col justify-center">
            <div class="flex flex-row justify-between  items-center">
              <p class="text-xs font-light">Pengaduan Selesai</p>
              <p class="text-xs font-light">12</p>
            </div>
            <div class="flex flex-row justify-between items-center">
              <p class="text-xs font-light">Pengaduan Belum Selesai</p>
              <p class="text-xs font-light">21</p>
            </div>
          </div>
        </div>
      </div>

      <div
        class="
          grid
          h-28
           border-gray-400
          rounded-xl
          mx-4
          bg-slate-200
          my-4
          border-2
border-dashed
        "
      >
      <ViewGridAddIcon class="h-8 w-8 fill-gray-500 place-self-center" />
      </div>
    </div>
    <div class="bg-white grow mt-4"></div>
    <div class="bg-slate-200 flex-none w-80"></div>
  </div>
 </div>
</template>

<script>
import { XIcon, ViewGridAddIcon } from "@heroicons/vue/solid";

import { PieChart } from "vue-chart-3";
import { Chart, registerables } from "chart.js";
import { ref } from "vue";

Chart.register(...registerables);

export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  components: { XIcon, PieChart, ViewGridAddIcon },
  data() {
    return {
      testData: {
        datasets: [
          {
            data: [30, 40],
            backgroundColor: ["#77CEFF", "#0079AF"],
          },
        ],
      },
      options: ref({
        responsive: true,
        plugins: {
          title: {
            display: false,
          },
        },
      }),
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
