<template>
  <div class="">
    <div class="max-w-sm w-full lg:max-w-full lg:flex content-center mx-50">
      <nuxt-link :to="'Search/' + name">
        <img class="h-32 w-32 flex-shrink-0" v-bind:src="imgUrl">
      </nuxt-link>
      <div class="border-r border-b border-l border-gray-400 lg:border-l-0 lg:border-t lg:border-gray-400 bg-white rounded-b lg:rounded-b-none lg:rounded-r p-4 flex flex-col justify-between leading-normal">
        <div class="mb-8">
          <p class="text-sm text-gray-600 flex items-center">
            <svg class="fill-current text-gray-500 w-3 h-3 mr-2" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20">
              <path d="M4 8V6a6 6 0 1 1 12 0v2h1a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H3a2 2 0 0 1-2-2v-8c0-1.1.9-2 2-2h1zm5 6.73V17h2v-2.27a2 2 0 1 0-2 0zM7 6v2h6V6a3 3 0 0 0-6 0z" />
            </svg>
            Members only
          </p>
          <div class="text-gray-900 font-bold text-xl mb-2"> {{ name }}</div>
          <p class="text-gray-700 text-base">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, nulla! Maiores et perferendis eaque, exercitationem praesentium nihil.</p>
        </div>
        <div class="flex items-center">
          <img class="w-10 h-10 rounded-full mr-4" src="/img/jonathan.jpg" alt="Avatar of Jonathan Reinink">
          <div class="text-sm">
            <p class="text-gray-900 leading-none">Jonathan Reinink</p>
            <p class="text-gray-600">Aug 18</p>
          </div>
        </div>
      </div>
      <div class="">
        <p>{{ name }}</p>
        <img class="h-32 w-32 flex-shrink-0" v-bind:src="imgUrl">
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