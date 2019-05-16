<template>
  <div class="content">
    <aside-nav/>
    <main class="main">
      <app-header/>
      <nuxt/>
    </main>
  </div>
</template>
<script>
  import AsideNav from '~/components/AsideNav.vue'
  import AppHeader from '~/components/AppHeader.vue'

  export default {
    components: {
      AppHeader,
      AsideNav
    }
  }
</script>
<style>
.content {
  min-height: 100vh;
  display: flex;
}

.main {
  flex: 1;
}
</style>

