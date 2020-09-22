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

    <div class="notifications notifications--has-notifications">
      <a href="#" class="notifications__toggler" ref="notifications__toggler">
        <span class="icon"><i class="fas fa-bell"></i></span>
      </a>

      <div class="notifications__content">
        <div class="notifications__header">
          <span class="notifications__header__title">Notifications</span>
          <a href="#" class="notifications__header__action">Mark all as read</a>
        </div>

        <div class="notifications__list">
          <div class="notifications__list__item notifications__list__item--checked">
            <div class="notifications__list__item__leading">
              <span class="icon icon-checked">
                <i class="fas fa-check"></i>
              </span>
            </div>

            <div class="notifications__list__item__content">
              <span class="notifications__list__item__content__title">
                <strong>Stephan Parker</strong> marked the task as done
              </span>

              <span class="notifications__list__item__content__time">a day ago</span>
            </div>
          </div>

          <div class="notifications__list__item">
            <div class="notifications__list__item__leading">
            </div>

            <div class="notifications__list__item__content">
              <span class="notifications__list__item__content__title">
                <strong>Steve O'Reilly</strong> answered to your comment on the Cash Flow Forecast's graph
              </span>

              <span class="notifications__list__item__content__time">a day ago</span>
            </div>
          </div>

          <div class="notifications__list__item">
            <div class="notifications__list__item__leading">
            </div>

            <div class="notifications__list__item__content">
              <span class="notifications__list__item__content__title">
                <strong>Sophie Welch</strong> mentionned you in her comment on Invoices
              </span>

              <span class="notifications__list__item__content__time">2 days ago</span>
            </div>
          </div>

          <div class="notifications__list__item">
            <div class="notifications__list__item__leading">
            </div>

            <div class="notifications__list__item__content">
              <span class="notifications__list__item__content__title">
                <strong>Sophie Welch</strong> mentionned you in her comment on Invoices
              </span>

              <span class="notifications__list__item__content__time">2 days ago</span>
            </div>
          </div>
        </div>

        <div class="notifications__footer">
          <a href="#" class="notifications__footer__action">View All</a>
        </div>
      </div>
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

    const notificationsToggler = this.$refs['notifications__toggler']
    notificationsToggler.addEventListener('click', () => {
      notificationsToggler.closest('.notifications')
        .classList.toggle('notifications--expand')
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

  &__user {
    display: flex;
    align-items: center;
    position: relative;
    user-select: none;

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

.notifications {
  background-color: white;
  display: flex;
  align-items: center;
  margin-left: auto;
  margin-right: .85rem;
  position: relative;
  height: 100%;

  &__content {
    display: flex;
    flex-direction: column;
    background-color: white;
    border-top: 1px solid rgba(0, 0, 0, 0.11);
    box-shadow: 0 1px 1px rgba(0, 0, 0, 0.11),
                0 2px 2px rgba(0, 0, 0, 0.11),
                0 4px 4px rgba(0, 0, 0, 0.11);
    position: fixed;
    top: calc(var(--app-navbar-height) - 4px);
    right: .5rem;
    width: 21.25rem;
    height: 80vh;
    transition: var(--app-transition-timing);
    visibility: hidden;
    opacity: 0;
  }

  &__header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem .75rem;

    &__title {
      color: #999;
      font-weight: bold;
      text-transform: uppercase;
    }
  }

  &__list {
    flex: 1;
    padding: 0 .75rem;
  }

  &__footer {
    background-color: rgba(0, 0, 0, 0.05);
    padding: .75rem 1rem;
    text-align: center;
  }

  &__header, &__footer {
    &__action {
      color: #2d57b3;
      font-weight: 700;
      text-decoration: none;
    }
  }

  &__list {
    overflow: auto;

    &__item {
      background-color: #fffaf0;
      border-radius: 5px;
      display: flex;
      align-items: center;
      margin-bottom: .25rem;
      padding: 1rem;
    }
  }

  &__list__item__leading {
    flex: 0 0 auto;
    border-radius: 50%;
    background-color: orange;
    color: white;
    margin-right: .75rem;
    width: 3rem;
    height: 3rem;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  &__list__item--checked &__list__item__leading {
    background-color: #648b46;
  }

  &__list__item__content {
    display: flex;
    flex-direction: column;

    &__title, &__time {
      color: #888;
    }

    &__title {
      strong {
        color: #555;
      }
    }
  }

  &__toggler {
    text-decoration: none;
    margin: .1rem;
    cursor: pointer;
    position: relative;

    .icon {
      background-color: rgba(200, 200, 200, .15);
      color: #6a6a6a;
      display: inline-block;
      border-radius: .5rem;
      width: 2rem;
      height: 2rem;
      display: flex;
      justify-content: center;
      align-items: center;
    
      &:hover {
        color: #333;
      }
    }
  }

  &--has-notifications &__toggler:after {
    content: '';
    display: block;
    width: .75rem;
    height: .75rem;
    background-color: coral;
    border-radius: 50%;
    position: absolute;
    top: 0;
    right: 0;
    transform: translate(20%, -20%);
  }
}

.notifications--expand .notifications__content {
  visibility: visible;
  opacity: 1;
}

@media screen and (min-width: 360px) {
  .notifications {
    &__content {
      width: 23.5rem;
    }
  }
}

@media screen and (min-width: 640px) {
  .notifications {
    &__content {
      width: 30rem;
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
