<template>
  <div class="flex pt-5">
    <div class="text-gray-600 font-thin">
      <button class="bg-gray-500 hover:bg-gray-900 text-white font-bold py-2 px-4 rounded my-2 mx-4">
        <nuxt-link to="/Search">Back to Search</nuxt-link>
      </button>
    </div>
    <div class="bg-gray-400 rounded-lg overflow-hidden shadow-lg">
      <div class="object-fill">
        <img src="../../../assets/pictures/nicer-image.jpg" />
      </div>
      <div class="p-4 text-center">
        <h3 class="top-0 font-semibold text-base xl:6xl lg:6xl md:xl sm:xl">{{ fact.name }}</h3>
        <div class="text-gray-700 text-base xl:lg lg:lg sm:sm uppercase">
          {{ fact.subregion }}
        </div>
      </div>
      <div class="flex justify-center text-center px-4 pb-4">
        <div class="flex-1">
          <!-- For calling codes -->
          <span class="font-semibold text-base xl:2xl lg:2xl sm:sm">Calling code(s):</span>
          <ol>
            <li class="font-thin text-base xl:lg lg:lg sm:xs" v-for="code in fact.callingCodes">+{{ code }}</li>
          </ol>
        </div>
        <div class="flex-1">
          <!-- for time zones -->
          <span class="font-semibold text-base xl:2xl sm:sm">Timezone(s):</span>
          <ol>
            <li class="font-thin text-base xl:lg sm:xs" v-for="tz in fact.timezones">{{ tz }}</li>
          </ol>
        </div>
        <div class="flex-1">
          <!-- for languages -->
          <span class="font-semibold text-base xl:2xl lg:2xl sm:sm">Language(s):</span>
          <ol>
            <li class="font-thin text-base xl:lg lg:lg sm:xs" v-for="lang in fact.languages">{{ lang.name }}({{ lang.nativeName }})</li>
          </ol>
        </div>
      </div>
    </div>
    <div>
      <!-- Third section for misc stuff -->
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import Info from '../../../components/Info';

export default {
  components: {
    Info
  },
  data() {
    return {
      fact: {}
    };
  },
  async created() {
    axios.get(`https://restcountries.eu/rest/v2/name/${this.$route.params.id}`)
      .then(res => this.fact = res.data[0])
      .catch(err => console.log(err));
  },
}
</script>

<style scoped>
ul {
  list-style-type: disc;
}
li {
  display: list-item;
}
</style>