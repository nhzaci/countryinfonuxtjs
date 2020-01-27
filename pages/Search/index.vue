<template>
  <div id="app" class="antialiased text-gray-900">
    <CountrySearch v-on:search-text="searchText" />
    <Info v-for="fact in facts" :key="fact.numericCode"
    :id="fact.name" :name="fact.name" :calling-codes="fact.callingCodes"
    :timezones="fact.timezones" :region="fact.subregion" :acode="fact.alpha2Code" />
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