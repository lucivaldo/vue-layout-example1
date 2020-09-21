<template>
  <div id="app">
    <AppNavbar/>
    <AppSidebar/>

    <main class="main">
      <router-view/>
    </main>
  </div>
</template>

<script>
import AppSidebar from './components/layout/AppSidebar'
import AppNavbar from './components/layout/AppNavbar'

export default {
  name: 'App',

  components:  {
    AppSidebar,
    AppNavbar,
  }
}
</script>
