<template>
  <div class="app-navbar">
    <div class="app-sidebar__show" ref="app-sidebar__show">
      <span class="icon"><i class="fas fa-bars"></i></span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AppNavbar',

  mounted() {
    const appSidebarToggle = this.$refs['app-sidebar__show']

    appSidebarToggle.addEventListener('click', () => {
      document.body.classList.add('app-sidebar--show')
    })
  }
}
</script>

<style lang="scss">
:root {
  --app-navbar-height: 3rem;
}

.app-navbar {
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.11), 
              0 2px 2px rgba(0, 0, 0, 0.11), 
              0 4px 4px rgba(0, 0, 0, 0.11), 
              0 6px 8px rgba(0, 0, 0, 0.11),
              0 8px 16px rgba(0, 0, 0, 0.11);
  display: flex;
  align-items: center;
  height: var(--app-navbar-height);
  // overflow: hidden;
  padding: .5rem;

  .app-sidebar__show {
    display: inline-block;
    font-size: 1.15rem;
    padding: .15rem .65rem;
  }
}
</style>
