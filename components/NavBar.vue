<template>
  <header class="bg-gray-900">
    <!-- First part w logo and menu button -->
    <div class="flex justify-between px-4 py-3 items-center">
      <div class="flex items-center">
        <svg class="fill-current h-10 w-10 text-green-700" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 58 58"><circle cx="29" cy="29" r="29" fill="#7fabda"/>
          <path d="M43.887 4.486c.121-.042.219-.112.32-.179A28.858 28.858 0 0029 0a28.854 28.854 0 00-16.504 5.159c.025.116.057.231.108.341 1.978 4.262 4.523 11.496 8.869 13.163 2.113.81 4.066.505 6.069 1.486.214.104.527.348.661.545 1.018 1.489.432 3.671 1.442 4.205.799.422 1.253 1.285.912 2.122-1.393 3.418-.188 7.327 3.052 10.01 2.28 1.888.382 6.264-1.536 9.7-.686 1.229.537 2.648 1.862 2.177 2.096-.746 3.831-1.827 5.84-3.555 2.913-2.505 3.543-5.235 6.43-7.362a.182.182 0 00.069-.09c.738-2.164 3.031-6.887.717-8.09-2.16-1.122-2.968-4.371-5.076-6.585-.242-.254-.586-.38-.934-.425-2.584-.333-3.746-2.298-5.485-.991-1.302.979-2.766.383-3.22-1.182-.148-.51-.409-.965-1.346-1.254-.712-.219-1.058-1.026-.802-1.725l.011-.031c.343-.934-1.589-.792-2.571-.628-.275.046.659-1.065.352-.885-1.208.713-2.707-.518-2.643-1.919.066-1.421.331-1.353 2.767-1.633 2.622-1.221 3.891-.331 3.807 2.668 1.621.24 2.187-.476 1.699-2.149a1.637 1.637 0 01.282-1.437c2.988-3.886 5.483-5.58 10.055-7.149z" />
        </svg>
        <span class="h-full items-center text-white font-semibold pl-2 text-xl">Country.</span>
        <span class="text-blue-300 text-xl h-full font-semibold">Info</span>
      </div>
      <div>
        <button @click="isOpen = !isOpen" type="button" class="w-10 h-10 focus:text-white hover:text-white">
          <svg class="fill-current h-8 w-8 text-white" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 50 50">
            <path v-if="!isOpen" d="M0 3h50v2H0zM0 17h50v2H0zM0 31h50v2H0zM0 45h50v2H0z"/>
            <path v-if="isOpen" stroke="#fff" stroke-width="3" stroke-linecap="round" stroke-miterlimit="10" d="M16 34l9-9 9-9M16 16l9 9 9 9"/>
          </svg>
        </button>
      </div>
    </div>
    <!-- Second part: drop-down menu -->
    <div :class="isOpen ? 'block' : 'hidden'" class="px-4 pt-1 pb-4">
      <nuxt-link class="block text-white font-semibold rounded px-2 py-1 hover:bg-gray-800" to='/' v-on:click.native>Home</nuxt-link>
      <nuxt-link class="block text-white font-semibold rounded px-2 py-1 hover:bg-gray-800" to='/about'>About</nuxt-link>
      <nuxt-link class="block text-white font-semibold rounded px-2 py-1 hover:bg-gray-800" to='/Search'>Search</nuxt-link>
    </div>
  </header>
</template>

<script>
export default {
  name: "NavBar",
  data() {
    return {
      isOpen: false,
    }
  }
}
</script>

<style>

</style>