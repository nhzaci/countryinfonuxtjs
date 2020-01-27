<template>
  <nuxt-link :to="'search/' + name">
    <div class="bg-gray-400 rounded-lg overflow-hidden shadow-lg">
      <div class="object-fill">
        <img src="../assets/pictures/nicer-image.jpg" />
      </div>
      <div class="p-4">
        <h3 class="sticky top-0 font-semibold text-2xl">{{ name }}</h3>
        <div class="text-gray-700 text-xs uppercase">
          {{ region }}
        </div>
      </div>
    </div>
  </nuxt-link>
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