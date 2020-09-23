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
:root {
  --bg-color: white;
  --main-bg-color: white;
  --main-text-color: #333;

  --headings-text-color: var(--main-text-color);
  --headings-text-hover-color: #000;
}

body {
  background-color: var(--bg-color);
}

#main {
  background-color: var(--main-bg-color);
  color: var(--main-text-color);
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

.app-sidebar--shrink.app-sidebar__nav--overflow #main {
  margin-left: calc(5rem - 4px);
}

.app-sidebar--shrink.app-sidebar__nav--overflow.app-sidebar--hide-desktop #main {
  margin-left: 0;
}

@media screen and (min-width: 1024px) {
  #main {
    margin-left: var(--app-sidebar-width);
  }
}
</style>
