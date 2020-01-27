<template>
  <div class="flex justify-center w-full">
    <form class="w-full max-w-sm" @submit.prevent="onSubmit">
      <div class="flex items-center border-b border-b-2 border-gray-500 py-2">
        <input class="appearance-none bg-transparent border-none w-full text-gray-900 mr-3 px-1 leading-tight focus:outline-none" type="text" v-model="text" placeholder="Search countries here..." aria-label="">
        <button class="flex-shrink-0 bg-gray-500 hover:bg-gray-900 border-gray-500 hover: border-gray-900 text-sm border-4 text-white py-1 px-2 rounded" 
          type="submit">
          Search
        </button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "CountrySearch",
  data() {
    return {
      text: ''
    }
  },
  methods: {
    onSubmit() {
      this.$emit("search-text", this.text);
      this.text = '';
    }
  }
}
</script>

<style>

</style>