<template>
  <div class="flex justify-center">
    <div class="invisible sm:w-0">
      <!-- first block, used to center the middle content -->
    </div>
    <div id="app" class="antialiased text-gray-900">
      <div>
        <CountrySearch v-on:search-text="searchText" />
      </div>
      <div class="max-h-full">
        <Info class="my-2 mx-3" v-for="fact in facts" :key="fact.numericCode"
        :id="fact.name" :name="fact.name" :calling-codes="fact.callingCodes"
        :timezones="fact.timezones" :region="fact.subregion" :acode="fact.alpha2Code" />
      </div>
    </div>
    <div class="invisible sm:w-0">
      <!-- third block used to center the middle content -->
    </div>
  </div>
</template>

<script>
import Info from '../../components/Info';
import CountrySearch from '../../components/CountrySearch';
import axios from 'axios';

export default {
  components: {
    Info,
    CountrySearch
  },
  data() {
    return {
      facts: []
    }
  },
  async created() {
    try {
      const res = await axios.get('https://restcountries.eu/rest/v2/all');
      this.facts = res.data;
    } catch (err) {
      console.log(err);
    }
  },
  methods: {
    async searchText(text) {
      try {
        const res = await axios.get(`https://restcountries.eu/rest/v2/name/${text}`);
        this.facts = res.data;
      } catch (err) {
        console.log(err);
      }
    }
  }
}
</script>

<style>

</style>