<template>
  <div class="body">
    <nuxt-link to="/Search">Back to Search</nuxt-link>
    <h1>{{fact.name}}</h1>
    <h3>Region: {{fact.subregion}}</h3>
    <p>
      Calling Code(s): 
      <ul>
        <li v-for="code in fact.callingCodes" :key="code">
          {{ code }}
        </li>
      </ul>
    </p>
    <p>
      Time Zone(s):
      <ul>
        <li v-for="tz in fact.timezones" :key="tz">
          {{ tz }}
        </li>
      </ul>
    </p>
          Language(s):
      <ul>
        <li v-for="lang in fact.languages" :key="lang">
          {{ lang.name }} ({{ lang.nativeName }})
        </li>
      </ul>
    </p>
    <img v-bind:src="imgUrl">
  </div>
</template>

<script>
import axios from 'axios';

export default {
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