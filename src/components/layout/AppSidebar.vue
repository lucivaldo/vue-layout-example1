<template>
  <div class="app-sidebar">
    <ul class="app-nav">
      <header class="app-nav__header">
        <span class="app-nav__header__icon icon-leading"><i class="fas fa-layer-group"></i></span>
        <span class="app-nav__header__title">App Name</span>
        <span class="app-nav__header__icon icon-trailing"></span>

        <span class="icon app-sidebar__hide" ref="app-sidebar__hide">
          <i class="fas fa-align-left"></i>
        </span>
      </header>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-home"></i></span>
          <span class="app-sidebar__link__text">Home</span>
        </a>
      </li>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-dolly-flatbed"></i></span>
          <span class="app-sidebar__link__text">Controle Almoxarifado</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__item-status">
              <i class="fas fa-chevron-down"></i>
            </span>
          </span>
        </a>
      </li>

      <li class="app-sidebar__item app-sidebar__item--active">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-house-user"></i></span>
          <span class="app-sidebar__link__text">Controle Patrimonial</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__notification">
              12
            </span>
            <span class="icon-trailing__item-status">
              <i class="fas fa-chevron-down"></i>
            </span>
          </span>
        </a>
      </li>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-comment-dollar"></i></span>
          <span class="app-sidebar__link__text">Diárias</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__item-status">
              <i class="fas fa-chevron-down"></i>
            </span>
          </span>
        </a>
      </li>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-atlas"></i></span>
          <span class="app-sidebar__link__text">EDOC</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__item-status">
              <i class="fas fa-chevron-down"></i>
            </span>
          </span>
        </a>
      </li>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-dollar-sign"></i></span>
          <span class="app-sidebar__link__text">Financeiro</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__item-status">
              <i class="fas fa-chevron-down"></i>
            </span>
          </span>
        </a>
      </li>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-hand-holding-usd"></i></span>
          <span class="app-sidebar__link__text">Folha de Pagamento</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__item-status">
              <i class="fas fa-chevron-down"></i>
            </span>
          </span>
        </a>
      </li>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-smile"></i></span>
          <span class="app-sidebar__link__text">Gestão de Pessoas</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__item-status">
              <i class="fas fa-chevron-down"></i>
            </span>
          </span>
        </a>
      </li>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-money-check-alt"></i></span>
          <span class="app-sidebar__link__text">Indenizações</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__item-status">
              <i class="fas fa-chevron-down"></i>
            </span>
          </span>
        </a>
      </li>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-cogs"></i></span>
          <span class="app-sidebar__link__text">Painel de Controle</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__item-status">
              <i class="fas fa-chevron-down"></i>
            </span>
          </span>
        </a>
      </li>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-id-card-alt"></i></span>
          <span class="app-sidebar__link__text">Portal do Servidor</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__item-status">
              <i class="fas fa-chevron-down"></i>
            </span>
          </span>
        </a>
      </li>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-users"></i></span>
          <span class="app-sidebar__link__text">Recursos Humanos</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__item-status">
              <i class="fas fa-chevron-down"></i>
            </span>
          </span>
        </a>
      </li>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-store-alt"></i></span>
          <span class="app-sidebar__link__text">Subdefensoria</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__item-status">
              <i class="fas fa-chevron-down"></i>
            </span>
          </span>
        </a>
      </li>

      <div class="app-nav__footer">
        <li class="app-sidebar__divider"></li>

        <ul class="app-nav__footer__nav">
          <li class="app-sidebar__item">
            <a href="#" class="app-sidebar__link">
              <span class="icon icon-leading"><i class="fas fa-cog"></i></span>
              <span class="app-sidebar__link__text">Ajustes</span>
              <span class="icon icon-trailing">
                <span class="icon-trailing__item-status">
                  <i class="fas fa-chevron-down"></i>
                </span>
              </span>
            </a>
          </li>

          <li class="app-sidebar__item">
            <a href="#" class="app-sidebar__link">
              <span class="icon icon-leading"><i class="fas fa-question-circle"></i></span>
              <span class="app-sidebar__link__text">Ajuda</span>
              <span class="icon icon-trailing">
                <span class="icon-trailing__item-status">
                  <i class="fas fa-chevron-down"></i>
                </span>
              </span>
            </a>
          </li>

          <li class="app-sidebar__divider"></li>

          <li class="app-sidebar__item">
            <a href="#" class="app-sidebar__link app-sidebar__toggle-shrink" ref="app-sidebar__toggle-shrink">
              <span class="icon icon-leading"><i class="fas fa-expand"></i></span>
            </a>
          </li>
        </ul>
      </div>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'AppSidebar',

  mounted() {
    const appSidebarToggle = this.$refs['app-sidebar__hide']
    appSidebarToggle.addEventListener('click', () => {
      document.body.classList.remove('app-sidebar--show')
    })
    
    const appSidebarToggleShrink = this.$refs['app-sidebar__toggle-shrink']
    appSidebarToggleShrink.addEventListener('click', () => {
      document.body.classList.toggle('app-sidebar--shrink')
    })
  }
}
</script>

<style lang="scss">
:root {
  --app-sidebar-background-color: #112cd3;
  --app-sidebar-width: 20rem;
  --app-sidebar-icon-font-size: 1.2rem;
  --app-sidebar-icon-width: 2rem;
  --app-sidebar-divider-color: rgba(44, 44, 44, .45);
}

.app-sidebar {
  position: fixed;
  top: 0;
  left: 0;
  height: 100%;
  transition: .4s cubic-bezier(0.165, 0.84, 0.44, 1);
  transform: translateX(-100%);
  width: 90%;
  overflow: hidden;
}

.app-sidebar--show .app-sidebar {
  transform: translateX(0);
}

.app-sidebar--shrink .app-sidebar {
  width: calc(1rem + var(--app-sidebar-icon-width) + .75rem);
  overflow: hidden;

  .app-nav__header {
    position: relative;

    &__icon:not(.icon-trailing), &__title {
      display: none;
    }
  }
}

.app-sidebar--show.app-sidebar--shrink .app-sidebar {
  overflow: hidden;

  &__hide {
    position: absolute;
    left: 0;
    top: 50%;
    transform: translate(calc(50% - .4rem), -50%);
  }
}

.app-nav {
  background-color: var(--app-sidebar-background-color, #112cd3);
  width: var(--app-sidebar-width, 20rem);
  height: 100%;
}

.app-sidebar {
  &__item {
    display: block;
  }

  &__link {
    color: white;
    display: flex;
    align-items: center;
    padding: .85rem 1rem;
    text-decoration: none;
    transition: .3s;
    white-space: nowrap;

    .icon-leading {
      display: inline-block;
      text-align: center;
      margin-right: .75rem;
      width: var(--app-sidebar-icon-width);
      font-size: var(--app-sidebar-icon-font-size);
    }

    .icon-trailing {
      display: flex;
      margin-left: auto;
    }

    .icon-trailing__notification {
      background-color: white;
      border-radius: 50%;
      color: #333;
      font-size: .8rem;
      font-weight: 800;
      width: 1.15rem;
      height: 1.15rem;
      display: flex;
      justify-content: center;
      align-items: center;
      margin-right: .5rem;
    }

    .icon-trailing__item-status {
      font-size: .9em;
    }

    // Estilos para o ícone de notificação quando o
    // mouse passar por cima do ítem.
    // &:hover .icon-trailing__notification {
    //   background-color: var(--app-sidebar-background-color);
    //   color: white;
    //   width: 1.3rem;
    //   height: 1.3rem;
    // }
  }

  &__link:hover, &__item--active {
    background-color: #040609;
  }

  &__divider {
    border-bottom: 1px solid var(--app-sidebar-divider-color);
    display: block;
  }
}

.app-nav {
  overflow-y: auto;
  overflow-x: hidden;

  &__header {
    border-bottom: 1px solid var(--app-sidebar-divider-color);
    display: flex;
    align-items: center;
    padding: 1.65rem 1rem;

    .icon-leading {
      background-color: white;
      border-radius: 555%;
      color: var(--app-sidebar-background-color, #112cd3);
      display: inline-flex;
      font-size: var(--app-sidebar-icon-font-size);
      justify-content: center;
      align-items: center;
      width: var(--app-sidebar-icon-width);
      height: var(--app-sidebar-icon-width);
      margin-right: .75rem;
    }

    &__title {
      color: white;
      font-size: 1.25rem;
      white-space: nowrap;
    }

    .app-sidebar__hide {
      color: white;
      margin-left: auto;
      display: inline-block;
      font-size: 1.15rem;
      padding: .15rem .65rem;
    }
  }
}
</style>
