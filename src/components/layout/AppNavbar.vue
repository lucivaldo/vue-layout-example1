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

    <div class="app-theme-toggle">
      <input type="checkbox"
        class="app-theme-toggle__toggler"
        id="app-theme-toggle__toggler"
        ref="app-theme-toggle__toggler"
        >
      <label for="app-theme-toggle__toggler"></label>
    </div>

    <div class="notifications notifications--has-notifications" ref="notifications">
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

    const notifications = this.$refs.notifications
    document.addEventListener('click', (event) => {
      if (!notifications.contains(event.target)) {
        notifications.classList.remove('notifications--expand')
      }
    })

    this.configureTheme()
  },

  methods: {
    configureTheme() {
      const getStyle = (element, property) => {
        return window
          .getComputedStyle(element)
          .getPropertyValue(property)
      }

      const root = document.querySelector(':root')

      const initialColors = {
        appNavbarBgColor: getStyle(root, '--app-navbar-bg-color'),
        appNavbarTextColor: getStyle(root, '--app-navbar-text-color'),
        appNavbarUserNameColor: getStyle(root, '--app-navbar-user-name-color'),
        appNavbarUserNameHoverColor: getStyle(root, '--app-navbar-user-name-hover-color'),
        appNavbarUserRoleColor: getStyle(root, '--app-navbar-user-role-color'),
        appNavbarUserRoleHoverColor: getStyle(root, '--app-navbar-user-role-hover-color'),
        appNavbarUserToggleActionsColor: getStyle(root, '--app-navbar-user-toggle-actions-color'),
        appNavbarUserToggleActionsHoverColor: getStyle(root, '--app-navbar-user-toggle-actions-hover-color'),

        notificationsBgColor: getStyle(root, '--notifications-bg-color'),
        notificationsBoxShadowColor: getStyle(root, '--notifications-box-shadow-color'),
        notificationsHeaderTitleColor: getStyle(root, '--notifications-header-title-color'),
        notificationsFooterBgColor: getStyle(root, '--notifications-footer-bg-color'),
        notificationsActionLinkColor: getStyle(root, '--notifications-action-link-color'),
        notificationsActionLinkHoverColor: getStyle(root, '--notifications-action-link-hover-color'),
        notificationsListItemBgColor: getStyle(root, '--notifications-list-item-bg-color'),
        notificationsListItemLeadingBgColor: getStyle(root, '--notifications-list-item-leading-bg-color'),
        notificationsListItemLeadingTextColor: getStyle(root, '--notifications-list-item-leading-text-color'),
        notificationsListItemLeadingCheckedBgColor: getStyle(root, '--notifications-list-item-leading-checked-bg-color'),
        notificationsListItemLeadingCheckedTextColor: getStyle(root, '--notifications-list-item-leading-checked-text-color'),
        notificationsListItemContentTitleColor: getStyle(root, '--notifications-list-item-content-title-color'),
        notificationsListItemContentTimeColor: getStyle(root, '--notifications-list-item-content-time-color'),
        notificationsListItemContentTitleStrongColor: getStyle(root, '--notifications-list-item-content-title-strong-color'),
        notificationsTogglerIconBgColor: getStyle(root, '--notifications-toggler-icon-bg-color'),
        notificationsTogglerIconColor: getStyle(root, '--notifications-toggler-icon-color'),
        notificationsTogglerIconBgHoverColor: getStyle(root, '--notifications-toggler-icon-bg-hover-color'),
        notificationsTogglerIconHoverColor: getStyle(root, '--notifications-toggler-icon-hover-color'),
        notificationsHasNotificationsTogglerIndicatorBgColor: getStyle(root, '--notifications-has-notifications-toggler-indicator-bg-color'),

        appNavbarUserActionsBgColor: getStyle(root, '--app-navbar-user-actions-bg-color'),
        appNavbarUserActionsBoxShadowColor: getStyle(root, '--app-navbar-user-actions-box-shadow-color'),
        appNavbarUserActionsItemBgColor: getStyle(root, '--app-navbar-user-actions-item-bg-color'),
        appNavbarUserActionsItemBgHoverColor: getStyle(root, '--app-navbar-user-actions-item-bg-hover-color'),
        appNavbarUserActionsItemColor: getStyle(root, '--app-navbar-user-actions-item-color'),
        appNavbarUserActionsItemHoverColor: getStyle(root, '--app-navbar-user-actions-item-hover-color'),

        appSidebarBgColor: getStyle(root, '--app-sidebar-bg-color'),
        appSidebarDividerColor: getStyle(root, '--app-sidebar-divider-color'),

        mainBgColor: getStyle(root, '--main-bg-color'),
        mainTextColor: getStyle(root, '--main-text-color'),

        headingsTextColor: getStyle(root, '--headings-text-color'),
        headingsTextHoverColor: getStyle(root, '--headings-text-hover-color'),
      }

      const darkMode = {
        appNavbarBgColor: '#333',
        appNavbarTextColor: 'white',
        appNavbarUserNameColor: 'white',
        appNavbarUserNameHoverColor: 'white',
        appNavbarUserRoleColor: 'white',
        appNavbarUserRoleHoverColor: 'white',
        appNavbarUserToggleActionsColor: 'white',
        appNavbarUserToggleActionsHoverColor: 'white',

        notificationsBgColor: '#333',
        notificationsBoxShadowColor: 'rgba(240, 240, 240, 0.85)',
        notificationsHeaderTitleColor: '#f5f5f5',
        notificationsFooterBgColor: 'white',
        // notificationsActionLinkColor: '',
        // notificationsActionLinkHoverColor: '',
        notificationsListItemBgColor: '#444',
        // notificationsListItemLeadingBgColor: '',
        // notificationsListItemLeadingTextColor: '',
        // notificationsListItemLeadingCheckedBgColor: '',
        // notificationsListItemLeadingCheckedTextColor: '',
        notificationsListItemContentTitleColor: 'white',
        notificationsListItemContentTimeColor: 'white',
        notificationsListItemContentTitleStrongColor: '#efefef',
        // notificationsTogglerIconBgColor: '',
        // notificationsTogglerIconColor: '',
        // notificationsTogglerIconBgHoverColor: '',
        // notificationsTogglerIconHoverColor: '',
        // notificationsHasNotificationsTogglerIndicatorBgColor: '',

        appNavbarUserActionsBgColor: '#333',
        appNavbarUserActionsBoxShadowColor: 'rgba(200, 200, 200, .85)',
        appNavbarUserActionsItemBgColor: '#333',
        appNavbarUserActionsItemBgHoverColor: '#111',
        appNavbarUserActionsItemColor: 'white',
        appNavbarUserActionsItemHoverColor: 'white',

        appSidebarBgColor: '#333',
        appSidebarDividerColor: '#dedede',

        mainBgColor: '#333',
        mainTextColor: 'white',

        headingsTextColor: 'white',
        headingsTextHoverColor: 'white',
      }

      const transformKey = key => {
        return '--' + key.replace(/([A-Z])/g, "-$1").toLowerCase()
      }

      const changeColors = colors => {
        Object.keys(colors).map(key => {
          root.style.setProperty(transformKey(key), colors[key])
        })
      }

      const themeToggler = this.$refs['app-theme-toggle__toggler']
      themeToggler.addEventListener('click', () => {
        const checked = themeToggler.checked
        checked ? changeColors(darkMode) : changeColors(initialColors)
      })
    }
  }
}
</script>

<style lang="scss">
:root {
  --app-navbar-bg-color: #fff;
  --app-navbar-text-color: #555;
  --app-navbar-user-name-color: #555;
  --app-navbar-user-name-hover-color: #333;
  --app-navbar-user-role-color: #626262;
  --app-navbar-user-role-hover-color: #444;
  --app-navbar-user-toggle-actions-color: #6a6a6a;
  --app-navbar-user-toggle-actions-hover-color: #333;

  --app-navbar-user-actions-bg-color: white;
  --app-navbar-user-actions-box-shadow-color: rgba(0, 0, 0, 0.11);
  --app-navbar-user-actions-item-bg-color: white;
  --app-navbar-user-actions-item-bg-hover-color: rgba(0, 0, 0, 0.05);
  --app-navbar-user-actions-item-color: #333;
  --app-navbar-user-actions-item-hover-color: #000;

  --notifications-bg-color: white;
  --notifications-box-shadow-color: rgba(0, 0, 0, 0.11);
  --notifications-header-title-color: #999;
  --notifications-footer-bg-color: rgba(0, 0, 0, 0.05);
  --notifications-action-link-color: #2886C9;
  --notifications-action-link-hover-color: #2d57b3;
  --notifications-list-item-bg-color: #fffaf0;
  --notifications-list-item-leading-bg-color: orange;
  --notifications-list-item-leading-text-color: white;
  --notifications-list-item-leading-checked-bg-color: #648b46;
  --notifications-list-item-leading-checked-text-color: white;
  --notifications-list-item-content-title-color: #888;
  --notifications-list-item-content-time-color: #888;
  --notifications-list-item-content-title-strong-color: #555;
  --notifications-toggler-icon-bg-color: rgba(200, 200, 200, .15);
  --notifications-toggler-icon-color: #6a6a6a;
  --notifications-toggler-icon-bg-hover-color: rgba(100, 100, 100, .15);
  --notifications-toggler-icon-hover-color: #333;
  --notifications-has-notifications-toggler-indicator-bg-color: tomato;

  --app-navbar-height: 3.75rem;
}

.app-navbar {
  background-color: var(--app-navbar-bg-color);
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
    color: var(--app-navbar-text-color);
    display: inline-block;
    font-size: 1.15rem;
    padding: .15rem .65rem;

    &:hover {
      cursor: pointer;
    }
  }

  &__app {
    color: var(--app-navbar-text-color);
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
      color: var(--app-navbar-user-name-color);
      font-weight: bold;
      letter-spacing: 1px;

      &:hover {
        color: var(--app-navbar-user-name-hover-color);
      }
    }

    &__role {
      color: var(--app-navbar-user-role-color);
      font-weight: bold;
      font-size: .75rem;
      letter-spacing: 1px;

      &:hover {
        color: var(--app-navbar-user-role-hover-color);
      }
    }

    &__toggle-actions .icon {
      color: var(--app-navbar-user-toggle-actions-color);
      padding: .5rem;

      &:hover {
        color: var(--app-navbar-user-toggle-actions-hover-color);
        cursor: pointer;
      }
    }

    &__actions {
      background-color: var(--app-navbar-user-actions-bg-color);
      border-top: 1px solid var(--app-navbar-user-actions-box-shadow-color);
      box-shadow: 0 1px 1px var(--app-navbar-user-actions-box-shadow-color),
                  0 2px 2px var(--app-navbar-user-actions-box-shadow-color),
                  0 4px 4px var(--app-navbar-user-actions-box-shadow-color);
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
        background-color: var(--app-navbar-user-actions-item-bg-color);
        color: var(--app-navbar-user-actions-item-color);
        padding: .75rem 1rem;
        border-radius: 5px;

        &:hover {
          background-color: var(--app-navbar-user-actions-item-bg-hover-color);
          color: var(--app-navbar-user-actions-item-hover-color);
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

.app-theme-toggle {
  display: flex;
  align-items: center;
  margin-left: auto;
  position: relative;

  input {
    display: none;
    position: absolute;
    top: 0;
    left: 0;
    opacity: 0;
    z-index: -1;
  }

  label {
    background-color: #c4cad7;
    display: inline-block;
    width: 2.8rem;
    height: 1.55rem;
    border-radius: .75rem;
    margin: 0 1rem;
    position: relative;
    box-shadow: 1px 1px 1px rgba(100, 100, 100, 0.5);
  }

  label:after {
    content: '';
    display: block;
    width: 1.1rem;
    height: 1.1rem;
    background-color: white;
    position: absolute;
    left: 0;
    top: 0;
    border-radius: 50%;
    transform: translate(5px, 4px);
    transition: var(--app-transition-timing);
  }

  label:hover {
    background-color: #aea9b5;
    cursor: pointer;
  }

  input:checked ~ label {
    background-color: #453f2a;

    &:after {
      transform: translate(calc(100% + 4px), 4px);
    }
  }
}

.notifications {
  background-color: var(--notifications-bg-color);
  display: flex;
  align-items: center;
  margin-right: .85rem;
  position: relative;
  height: 100%;

  &__content {
    display: flex;
    flex-direction: column;
    background-color: inherit;
    border-top: 1px solid var(--notifications-box-shadow-color);
    box-shadow: 0 1px 1px var(--notifications-box-shadow-color),
                0 2px 2px var(--notifications-box-shadow-color),
                0 4px 4px var(--notifications-box-shadow-color);
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
      color: var(--notifications-header-title-color);
      font-weight: bold;
      text-transform: uppercase;
    }
  }

  &__list {
    flex: 1;
    padding: 0 .75rem;
  }

  &__footer {
    background-color: var(--notifications-footer-bg-color);
    padding: .75rem 1rem;
    text-align: center;
  }

  &__header, &__footer {
    &__action {
      color: var(--notifications-action-link-color);
      font-weight: 700;
      text-decoration: none;

      &:hover {
        color: var(--notifications-action-link-hover-color);
      }
    }
  }

  &__list {
    overflow: auto;

    &__item {
      background-color: var(--notifications-list-item-bg-color);
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
    color: var(--notifications-list-item-leading-text-color);
    margin-right: .75rem;
    width: 3rem;
    height: 3rem;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  &__list__item--checked &__list__item__leading {
    background-color: var(--notifications-list-item-leading-checked-bg-color);
    color: var(--notifications-list-item-leading-checked-text-color);
  }

  &__list__item__content {
    display: flex;
    flex-direction: column;

    &__title {
      color: var(--notifications-list-item-content-title-color);
    }

    &__time {
      color: var(--notifications-list-item-content-time-color);
    }

    &__title {
      strong {
        color: var(--notifications-list-item-content-title-strong-color);
      }
    }
  }

  &__toggler {
    text-decoration: none;
    margin: .1rem;
    cursor: pointer;
    position: relative;

    .icon {
      background-color: var(--notifications-toggler-icon-bg-color);
      color: var(--notifications-toggler-icon-color);
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
    background-color: var(--notifications-has-notifications-toggler-indicator-bg-color);
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

  .app-sidebar--show.app-sidebar--shrink .app-navbar__app {
    margin-left: 2rem;
  }
}

@media screen and (min-width: 972px) {
  .app-sidebar--show .app-navbar__app {
    margin-left: calc(var(--app-sidebar-width) - 2rem);
  }

  .app-sidebar--show.app-sidebar--shrink .app-navbar__app {
    margin-left: 2rem;
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
