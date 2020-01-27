<template>
  <div>
    <div>
      <NavBar/>
    </div>
    <nuxt />
    <div>
      <AppFooter class="inset-x-0 bottom-0 h-6" />
    </div>
  </div>
</template>

<script>
import NavBar from '../components/NavBar';
import AppFooter from '../components/AppFooter';

export default {
  components: {
    NavBar,
    AppFooter
  }
}
</script>

<style>
</style>
