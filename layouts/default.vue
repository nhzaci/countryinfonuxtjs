<template>
  <div>
    <NavBar />
    <nuxt />
    <AppFooter />
  </div>
</template>

<script>
import NavBar from '../components/NavBar';
import AppHeader from '../components/AppHeader';
import AppFooter from '../components/AppFooter';

export default {
  components: {
    NavBar,
    AppHeader,
    AppFooter
  }
}
</script>

<style>
</style>
