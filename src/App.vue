<template>
  <div id="app">
    <AppNavbar/>
    <AppSidebar/>
    <router-view/>
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
