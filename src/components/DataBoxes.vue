<template>
<div class="grid md:grid-cols-3 gap-4">
    <div class="shadow-bd bg-blue-100 p-10 text-center rounded">
        <h3 class="text-3xl text-black-800 font-bold mb-4">Cases</h3>
        <div class="text-2xl mb-4">
            <span class="font-bold">New:</span>
            {{numberWithCommas(stats.NewConfirmed)}}
        </div>
        <div class="text-2xl mb-4">
            <span class="font-bold">Total:</span>
            {{numberWithCommas(stats.TotalConfirmed)}}
        </div>
    </div>
    <div class="shadow-bd bg-red-100 p-10 text-center rounded">
        <h3 class="text-3xl text-black-800 font-bold mb-4">Deaths</h3>
        <div class="text-2xl mb-4">
            <span class="font-bold">New:</span>
            {{numberWithCommas(stats.NewDeaths)}}
        </div>
        <div class="text-2xl mb-4">
            <span class="font-bold">Total:</span>
            {{numberWithCommas(stats.TotalDeaths)}}
        </div>
    </div>
    <div class="shadow-bd bg-green-100 p-10 text-center rounded">
        <h3 class="text-3xl text-black-800 font-bold mb-4">Recovered</h3>
        <div class="text-2xl mb-4">
            <span class="font-bold">New:</span>
            {{numberWithCommas(stats.NewRecovered)}}
        </div>
        <div class="text-2xl mb-4">
            <span class="font-bold">Total:</span>
            {{numberWithCommas(stats.TotalRecovered)}}
        </div>
    </div>
</div>

</template>


<script>
export default {
    name:'DataBoxes',
    props:['stats'],
    setup () {
    return {
      numberWithCommas (x) {
        return x.toString()
          .replace(/\B(?=(\d{3})+(?!\d))/g, ',');
      }
    };
  }
};
</script>