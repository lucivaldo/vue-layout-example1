<template>
  <div class="app-sidebar">
    <ul class="app-nav">
      <header class="app-nav__header">
        <span class="app-nav__header__icon icon-leading"><i class="fas fa-layer-group"></i></span>
        <span class="app-nav__header__title">App Name</span>
        <span class="app-nav__header__icon icon-trailing"></span>
      </header>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-home"></i></span>
          <span class="app-sidebar__link__text">Home</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__notification"></span>
            <span class="icon-trailing__item-status"></span>
          </span>
        </a>
      </li>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-dolly-flatbed"></i></span>
          <span class="app-sidebar__link__text">Controle Almoxarifado</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__notification"></span>
            <span class="icon-trailing__item-status"></span>
          </span>
        </a>
      </li>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-house-user"></i></span>
          <span class="app-sidebar__link__text">Controle Patrimonial</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__notification"></span>
            <span class="icon-trailing__item-status"></span>
          </span>
        </a>
      </li>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-comment-dollar"></i></span>
          <span class="app-sidebar__link__text">Diárias</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__notification"></span>
            <span class="icon-trailing__item-status"></span>
          </span>
        </a>
      </li>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-atlas"></i></span>
          <span class="app-sidebar__link__text">EDOC</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__notification"></span>
            <span class="icon-trailing__item-status"></span>
          </span>
        </a>
      </li>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-dollar-sign"></i></span>
          <span class="app-sidebar__link__text">Financeiro</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__notification"></span>
            <span class="icon-trailing__item-status"></span>
          </span>
        </a>
      </li>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-hand-holding-usd"></i></span>
          <span class="app-sidebar__link__text">Folha de Pagamento</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__notification"></span>
            <span class="icon-trailing__item-status"></span>
          </span>
        </a>
      </li>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-smile"></i></span>
          <span class="app-sidebar__link__text">Gestão de Pessoas</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__notification"></span>
            <span class="icon-trailing__item-status"></span>
          </span>
        </a>
      </li>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-money-check-alt"></i></span>
          <span class="app-sidebar__link__text">Indenizações</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__notification"></span>
            <span class="icon-trailing__item-status"></span>
          </span>
        </a>
      </li>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-cogs"></i></span>
          <span class="app-sidebar__link__text">Painel de Controle</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__notification"></span>
            <span class="icon-trailing__item-status"></span>
          </span>
        </a>
      </li>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-id-card-alt"></i></span>
          <span class="app-sidebar__link__text">Portal do Servidor</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__notification"></span>
            <span class="icon-trailing__item-status"></span>
          </span>
        </a>
      </li>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-users"></i></span>
          <span class="app-sidebar__link__text">Recursos Humanos</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__notification"></span>
            <span class="icon-trailing__item-status"></span>
          </span>
        </a>
      </li>

      <li class="app-sidebar__item">
        <a href="#" class="app-sidebar__link">
          <span class="icon icon-leading"><i class="fas fa-store-alt"></i></span>
          <span class="app-sidebar__link__text">Subdefensoria</span>
          <span class="icon icon-trailing">
            <span class="icon-trailing__notification"></span>
            <span class="icon-trailing__item-status"></span>
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
                <span class="icon-trailing__notification"></span>
                <span class="icon-trailing__item-status"></span>
              </span>
            </a>
          </li>

          <li class="app-sidebar__item">
            <a href="#" class="app-sidebar__link">
              <span class="icon icon-leading"><i class="fas fa-question-circle"></i></span>
              <span class="app-sidebar__link__text">Ajuda</span>
              <span class="icon icon-trailing">
                <span class="icon-trailing__notification"></span>
                <span class="icon-trailing__item-status"></span>
              </span>
            </a>
          </li>

          <li class="app-sidebar__divider"></li>

          <li class="app-sidebar__item">
            <a href="#" class="app-sidebar__link">
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
  name: 'AppSidebar'
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
}

.app-nav {
  background-color: var(--app-sidebar-background-color, #112cd3);
  width: var(--app-sidebar-width, 20rem);
  height: 100%;
}

.app-sidebar {
  &__item, &__link {
    display: block;
  }

  &__link {
    color: white;
    padding: .85rem 1rem;
    text-decoration: none;
    transition: .3s;

    &:hover {
      background-color: #040609;
    }

    .icon-leading {
      display: inline-block;
      text-align: center;
      margin-right: .75rem;
      width: var(--app-sidebar-icon-width);
      font-size: var(--app-sidebar-icon-font-size);
    }
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
    // margin-bottom: 1.65rem;
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
    }
  }
}
</style>
