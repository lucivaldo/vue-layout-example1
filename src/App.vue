<template>
  <div id="app">
    <AppNavbar/>
    <AppSidebar/>

    <main id="main">
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

<style lang="scss">
#main {
  margin-top: var(--app-navbar-height);
  padding: .75rem;
}

.app-sidebar--hide-desktop #main {
  margin-left: 0;
}

.app-sidebar--shrink #main {
  margin-left: calc(1rem + var(--app-sidebar-icon-width) + .75rem);
}

.app-sidebar--shrink.app-sidebar--hide-desktop #main {
  margin-left: 0;
}

.app-sidebar--shrink.app-sidebar--overflow #main {
  margin-left: calc(5rem - 4px);
}

.app-sidebar--shrink.app-sidebar--overflow.app-sidebar--hide-desktop #main {
  margin-left: 0;
}

@media screen and (min-width: 1024px) {
  #main {
    margin-left: var(--app-sidebar-width);
  }
}
</style>
