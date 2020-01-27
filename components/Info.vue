<template>
  <nuxt-link :to="'Search/' + name">
    <div>
      <p>{{ name }}</p>
      <img class="h-32 w-32 flex-shrink-0" src="resolve_img_url(`https://www.countryflags.io/${acode}/flat/32.png`)">
    </div>
  </nuxt-link>
</template>

<script>
export default {
  name: "Info",
  props:['name', 'region', 'timezones', 'calling-code',
    'id', 'acode'],
  
}
</script>

<style>
  .name {
    padding: 1rem;
    border: 1px dotted #ccc;
    margin: 1rem 0;
  }
</style>