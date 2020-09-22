<template>
  <div class="app-navbar">
    <div class="app-sidebar__show" ref="app-sidebar__show">
      <span class="icon"><i class="fas fa-bars"></i></span>
    </div>

    <div class="app-navbar__app">
      <div class="app-navbar__app__logo">
        <img src="../../assets/images/logo.svg" alt="App Logo">
      </div>

      <span class="app-navbar__app__name">App Name</span>
    </div>

    <div class="app-navbar__notifications">
      <span class="icon"><i class="fas fa-bell"></i></span>
    </div>

    <div class="app-navbar__user" ref="app-navbar__user">
      <div class="app-navbar__user__avatar">
        <img src="../../assets/images/profile.jpg" alt="User Avatar">
      </div>

      <div class="app-navbar__user__details">
        <span class="app-navbar__user__name">Lucivaldo Castro</span>
        <span class="app-navbar__user__role">Desenvolvedor</span>
      </div>

      <div class="app-navbar__user__toggle-actions" ref="app-navbar__user__toggle-actions">
        <span class="icon"><i class="fas fa-ellipsis-v"></i></span>
      </div>

      <div class="app-navbar__user__actions">
        <a href="#" class="app-navbar__user__actions__item">
          <span class="icon"><i class="fas fa-user"></i></span>
          Perfil
        </a>

        <a href="#" class="app-navbar__user__actions__item">
          <span class="icon"><i class="fas fa-sign-out-alt"></i></span>
          Logout
        </a>
      </div>
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
      document.body.classList.remove('app-sidebar--hide-desktop')
    })

    const appNavbarUser = this.$refs['app-navbar__user']
    document.addEventListener('click', event => {
      if (!appNavbarUser.contains(event.target)) {
        appNavbarUser.classList.remove('app-navbar__user--expand')
      }
    })

    const appNavBarUserActionsToggle = this.$refs['app-navbar__user__toggle-actions']
    appNavBarUserActionsToggle.addEventListener('click', () => {
      appNavBarUserActionsToggle.closest('.app-navbar__user')
        .classList.toggle('app-navbar__user--expand')
    })
  }
}
</script>

<style lang="scss">
:root {
  --app-navbar-height: 3.75rem;
}

.app-navbar {
  background-color: white;
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.11), 
              0 2px 2px rgba(0, 0, 0, 0.11), 
              0 4px 4px rgba(0, 0, 0, 0.11);
  display: flex;
  align-items: center;
  height: var(--app-navbar-height);
  padding: .5rem;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;

  .app-sidebar__show {
    display: inline-block;
    font-size: 1.15rem;
    padding: .15rem .65rem;

    &:hover {
      cursor: pointer;
    }
  }

  &__app {
    display: none;
  }

  &__notifications {
    display: flex;
    margin-left: auto;
    margin-right: 1rem;

    &__email, &__alerts {
      background-color: rgba(200, 200, 200, .15);
      border-radius: .5rem;
      color: #6a6a6a;
      width: 2rem;
      height: 2rem;
      display: flex;
      justify-content: center;
      align-items: center;
      margin: .4rem;
      cursor: pointer;

      &:hover {
        color: #333;
      }
    }
  }

  &__user {
    display: flex;
    align-items: center;
    position: relative;

    &__avatar {
      border: 3px solid rgba(10, 10, 10, .75);
      border-radius: 50%;
      width: 3rem;
      height: 3rem;
      margin: 0 .5rem;
      overflow: hidden;

      &:hover {
        border-color: #222;
      }
    }

    &__avatar img {
      width: 3rem;
      height: auto;
    }

    &__details {
      display: flex;
      flex-direction: column;
      margin-right: 1rem;
    }

    &__name {
      color: #555;
      font-weight: bold;
      letter-spacing: 1px;

      &:hover {
        color: #333;
      }
    }

    &__role {
      color: #626262;
      font-weight: bold;
      font-size: .75rem;
      letter-spacing: 1px;

      &:hover {
        color: #444;
      }
    }

    &__toggle-actions .icon {
      color: #6a6a6a;
      padding: .5rem;

      &:hover {
        color: #333;
        cursor: pointer;
      }
    }

    &__actions {
      background-color: white;
      border-top: 1px solid rgba(0, 0, 0, 0.11);
      box-shadow: 0 1px 1px rgba(0, 0, 0, 0.11),
                  0 2px 2px rgba(0, 0, 0, 0.11),
                  0 4px 4px rgba(0, 0, 0, 0.11);
      position: absolute;
      top: 100%;
      right: 0;
      padding: .5rem;
      width: 17.5rem;
      border-radius: 5px;
      transition: var(--app-sidebar-transition-timing);
      visibility: hidden;
      opacity: 0;
      z-index: -1;

      &__item {
        display: block;
        text-decoration: none;
        color: #333;
        padding: .75rem 1rem;
        border-radius: 5px;

        &:hover {
          background-color: rgba(0, 0, 0, 0.05);
          color: black;
        }
      }
    }

    &--expand &__actions {
      opacity: 1;
      visibility: visible;
      z-index: 1;
    }
  }
}

@media screen and (min-width: 530px) {
  .app-navbar {
    &__app {
      display: flex;
      align-items: center;
      transition: var(--app-sidebar-transition-timing);

      &__logo {
        border: 3px solid rgba(10, 10, 10, .75);
        border-radius: 50%;
        margin: 0 1rem;
        width: 3rem;
        height: 3rem;

        img {
          width: 3rem;
          height: auto;
        }
      }

      &__name {
        font-weight: bold;
        font-size: 1.35rem;
      }
    }
  }
}

@media screen and (min-width: 972px) {
  .app-sidebar--show .app-navbar__app {
    margin-left: calc(var(--app-sidebar-width) - 1rem);
  }

  .app-sidebar--hide-desktop .app-navbar__app {
    margin-left: 0;
  }
}

@media screen and (min-width: 1024px) {
  .app-navbar__app, .app-sidebar--show .app-navbar__app {
    margin-left: calc(var(--app-sidebar-width) - 2rem);
  }

  .app-sidebar--show.app-sidebar--shrink .app-navbar__app {
    margin-left: 1rem;
  }
}
</style>
