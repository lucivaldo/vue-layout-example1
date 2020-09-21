<template>
  <div id="app">
    <AppSidebar/>
    <router-view/>
  </div>
</template>

<script>
import AppSidebar from './components/layout/AppSidebar'

export default {
  name: 'App',

  components:  {
    AppSidebar,
  }
}
</script>
