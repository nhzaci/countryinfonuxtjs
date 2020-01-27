<template>
  <div class="bg-teal-500 border rounded-lg overflow-hidden">
    <div>
      <img class="p-6 h-full" v-bind:src="imgUrl">
    </div>
    <div class="p-6">
      <h3 class="font-semibold text-2xl">{{ name }}</h3>
      <div class="text-gray-700 text-xs uppercase">
        {{ region }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Info",
  props:['name', 'region', 'timezones', 'calling-code',
    'id', 'acode'],
  data() {
    return {
      imgUrl: `https://www.countryflags.io/${this.acode}/flat/64.png`
    }
  }
}
</script>

<style>
  .name {
    padding: 1rem;
    border: 1px dotted #ccc;
    margin: 1rem 0;
  }
</style>