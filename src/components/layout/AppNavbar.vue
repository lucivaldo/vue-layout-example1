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
        bodyBg: getStyle(root, '--body-bg'),
        appNavbarBg: getStyle(root, '--app-navbar-bg'),
        appNavbar: getStyle(root, '--app-navbar'),
        appNavbarUserName: getStyle(root, '--app-navbar-user-name'),
        appNavbarUserNameHover: getStyle(root, '--app-navbar-user-name-hover'),
        appNavbarUserRole: getStyle(root, '--app-navbar-user-role'),
        appNavbarUserRoleHover: getStyle(root, '--app-navbar-user-role-hover'),
        appNavbarUserToggleActions: getStyle(root, '--app-navbar-user-toggle-actions'),
        appNavbarUserToggleActionsHover: getStyle(root, '--app-navbar-user-toggle-actions-hover'),

        notificationsBg: getStyle(root, '--notifications-bg'),
        notificationsBoxShadow: getStyle(root, '--notifications-box-shadow'),
        notificationsHeaderTitle: getStyle(root, '--notifications-header-title'),
        notificationsFooterBg: getStyle(root, '--notifications-footer-bg'),
        notificationsActionLink: getStyle(root, '--notifications-action-link'),
        notificationsActionLinkHover: getStyle(root, '--notifications-action-link-hover'),
        notificationsListItemBg: getStyle(root, '--notifications-list-item-bg'),
        notificationsListItemLeading: getStyle(root, '--notifications-list-item-leading'),
        notificationsListItemLeadingBg: getStyle(root, '--notifications-list-item-leading-bg'),
        notificationsListItemLeadingChecked: getStyle(root, '--notifications-list-item-leading-checked'),
        notificationsListItemLeadingCheckedBg: getStyle(root, '--notifications-list-item-leading-checked-bg'),
        notificationsListItemContentTitle: getStyle(root, '--notifications-list-item-content-title'),
        notificationsListItemContentTime: getStyle(root, '--notifications-list-item-content-time'),
        notificationsListItemContentTitleStrong: getStyle(root, '--notifications-list-item-content-title-strong'),
        notificationsTogglerIcon: getStyle(root, '--notifications-toggler-icon'),
        notificationsTogglerIconHover: getStyle(root, '--notifications-toggler-icon-hover'),
        notificationsTogglerIconBg: getStyle(root, '--notifications-toggler-icon-bg'),
        notificationsTogglerIconBgHover: getStyle(root, '--notifications-toggler-icon-bg-hover'),
        notificationsHasNotificationsTogglerIndicatorBg: getStyle(root, '--notifications-has-notifications-toggler-indicator-bg'),

        appNavbarUserActionsBg: getStyle(root, '--app-navbar-user-actions-bg'),
        appNavbarUserActionsBoxShadow: getStyle(root, '--app-navbar-user-actions-box-shadow'),
        appNavbarUserActionsItemBg: getStyle(root, '--app-navbar-user-actions-item-bg'),
        appNavbarUserActionsItemBgHover: getStyle(root, '--app-navbar-user-actions-item-bg-hover'),
        appNavbarUserActionsItem: getStyle(root, '--app-navbar-user-actions-item'),
        appNavbarUserActionsItemHover: getStyle(root, '--app-navbar-user-actions-item-hover'),

        appSidebarBg: getStyle(root, '--app-sidebar-bg'),
        appSidebarDivider: getStyle(root, '--app-sidebar-divider'),

        mainBg: getStyle(root, '--main-bg'),
        mainText: getStyle(root, '--main-text'),

        headingText: getStyle(root, '--headings-text'),
        headingTextHover: getStyle(root, '--headings-text-hover'),
      }

      const darkMode = {
        bodyBg: '#333',
        appNavbar: 'white',
        appNavbarBg: '#333',
        appNavbarUserName: 'white',
        appNavbarUserNameHover: 'white',
        appNavbarUserRole: 'white',
        appNavbarUserRoleHover: 'white',
        appNavbarUserToggleActions: 'white',
        appNavbarUserToggleActionsHover: 'white',

        notificationsBg: '#333',
        notificationsBoxShadow: 'rgba(240, 240, 240, 0.85)',
        notificationsHeaderTitle: '#f5f5f5',
        notificationsFooterBg: 'white',
        // notificationsActionLink: '',
        // notificationsActionLinkHover: '',
        notificationsListItemBg: '#444',
        // notificationsListItemLeading: '',
        // notificationsListItemLeadingBg: '',
        // notificationsListItemLeadingChecked: '',
        // notificationsListItemLeadingCheckedBg: '',
        notificationsListItemContentTitle: 'white',
        notificationsListItemContentTime: 'white',
        notificationsListItemContentTitleStrong: '#efefef',
        // notificationsTogglerIcon: '',
        // notificationsTogglerIconHover: '',
        // notificationsTogglerIconBg: '',
        // notificationsTogglerIconBgHover: '',
        // notificationsHasNotificationsTogglerIndicatorBg: '',

        appNavbarUserActionsBg: '#333',
        appNavbarUserActionsBoxShadow: 'rgba(200, 200, 200, .85)',
        appNavbarUserActionsItem: 'white',
        appNavbarUserActionsItemHover: 'white',
        appNavbarUserActionsItemBg: '#333',
        appNavbarUserActionsItemBgHover: '#111',

        appSidebarBg: '#333',
        appSidebarDivider: '#dedede',

        mainBg: '#333',
        mainText: 'white',

        headingText: 'white',
        headingTextHover: 'white',
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
  --app-navbar: #555;
  --app-navbar-bg: #fff;
  --app-navbar-user-name: #555;
  --app-navbar-user-name-hover: #333;
  --app-navbar-user-role: #626262;
  --app-navbar-user-role-hover: #444;
  --app-navbar-user-toggle-actions: #6a6a6a;
  --app-navbar-user-toggle-actions-hover: #333;

  --app-navbar-user-actions-bg: white;
  --app-navbar-user-actions-box-shadow: rgba(0, 0, 0, 0.11);
  --app-navbar-user-actions-item-bg: white;
  --app-navbar-user-actions-item-bg-hover: rgba(0, 0, 0, 0.05);
  --app-navbar-user-actions-item: #333;
  --app-navbar-user-actions-item-hover: #000;

  --notifications-bg: white;
  --notifications-box-shadow: rgba(0, 0, 0, 0.11);
  --notifications-header-title: #999;
  --notifications-footer-bg: rgba(0, 0, 0, 0.05);
  --notifications-action-link: #2886C9;
  --notifications-action-link-hover: #2d57b3;
  --notifications-list-item-bg: #fffaf0;
  --notifications-list-item-leading: white;
  --notifications-list-item-leading-bg: orange;
  --notifications-list-item-leading-checked: white;
  --notifications-list-item-leading-checked-bg: #648b46;
  --notifications-list-item-content-title: #888;
  --notifications-list-item-content-time: #888;
  --notifications-list-item-content-title-strong: #555;
  --notifications-toggler-icon: #6a6a6a;
  --notifications-toggler-icon-hover: #333;
  --notifications-toggler-icon-bg: rgba(200, 200, 200, .15);
  --notifications-toggler-icon-bg-hover: rgba(100, 100, 100, .15);
  --notifications-has-notifications-toggler-indicator-bg: tomato;

  --app-navbar-height: 3.75rem;
}

.app-navbar {
  background-color: var(--app-navbar-bg);
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
    color: var(--app-navbar);
    display: inline-block;
    font-size: 1.15rem;
    padding: .15rem .65rem;

    &:hover {
      cursor: pointer;
    }
  }

  &__app {
    color: var(--app-navbar);
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
      color: var(--app-navbar-user-name);
      font-weight: bold;
      letter-spacing: 1px;

      &:hover {
        color: var(--app-navbar-user-name-hover);
      }
    }

    &__role {
      color: var(--app-navbar-user-role);
      font-weight: bold;
      font-size: .75rem;
      letter-spacing: 1px;

      &:hover {
        color: var(--app-navbar-user-role-hover);
      }
    }

    &__toggle-actions .icon {
      color: var(--app-navbar-user-toggle-actions);
      padding: .5rem;

      &:hover {
        color: var(--app-navbar-user-toggle-actions-hover);
        cursor: pointer;
      }
    }

    &__actions {
      background-color: var(--app-navbar-user-actions-bg);
      border-top: 1px solid var(--app-navbar-user-actions-box-shadow);
      box-shadow: 0 1px 1px var(--app-navbar-user-actions-box-shadow),
                  0 2px 2px var(--app-navbar-user-actions-box-shadow),
                  0 4px 4px var(--app-navbar-user-actions-box-shadow);
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
        background-color: var(--app-navbar-user-actions-item-bg);
        color: var(--app-navbar-user-actions-item);
        padding: .75rem 1rem;
        border-radius: 5px;

        &:hover {
          background-color: var(--app-navbar-user-actions-item-bg-hover);
          color: var(--app-navbar-user-actions-item-hover);
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
  background-color: var(--notifications-bg);
  display: flex;
  align-items: center;
  margin-right: .85rem;
  position: relative;
  height: 100%;

  &__content {
    display: flex;
    flex-direction: column;
    background-color: inherit;
    border-top: 1px solid var(--notifications-box-shadow);
    box-shadow: 0 1px 1px var(--notifications-box-shadow),
                0 2px 2px var(--notifications-box-shadow),
                0 4px 4px var(--notifications-box-shadow);
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
      color: var(--notifications-header-title);
      font-weight: bold;
      text-transform: uppercase;
    }
  }

  &__list {
    flex: 1;
    padding: 0 .75rem;
  }

  &__footer {
    background-color: var(--notifications-footer-bg);
    padding: .75rem 1rem;
    text-align: center;
  }

  &__header, &__footer {
    &__action {
      color: var(--notifications-action-link);
      font-weight: 700;
      text-decoration: none;

      &:hover {
        color: var(--notifications-action-link-hover);
      }
    }
  }

  &__list {
    overflow: auto;

    &__item {
      background-color: var(--notifications-list-item-bg);
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
    color: var(--notifications-list-item-leading);
    margin-right: .75rem;
    width: 3rem;
    height: 3rem;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  &__list__item--checked &__list__item__leading {
    background-color: var(--notifications-list-item-leading-checked-bg);
    color: var(--notifications-list-item-leading-checked);
  }

  &__list__item__content {
    display: flex;
    flex-direction: column;

    &__title {
      color: var(--notifications-list-item-content-title);
    }

    &__time {
      color: var(--notifications-list-item-content-time);
    }

    &__title {
      strong {
        color: var(--notifications-list-item-content-title-strong);
      }
    }
  }

  &__toggler {
    text-decoration: none;
    margin: .1rem;
    cursor: pointer;
    position: relative;

    .icon {
      background-color: var(--notifications-toggler-icon-bg);
      color: var(--notifications-toggler-icon);
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
    background-color: var(--notifications-has-notifications-toggler-indicator-bg);
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
