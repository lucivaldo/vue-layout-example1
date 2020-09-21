<template>
  <div id="app">
    <AppSidebar/>
    <AppNavbar/>
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
