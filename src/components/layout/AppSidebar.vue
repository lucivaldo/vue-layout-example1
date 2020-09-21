<template>
  <ul class="app-sidebar">
    <header class="app-sidebar__header">
      <span class="app-sidebar__header__icon icon-leading"><i class="fas fa-layer-group"></i></span>
      <span class="app-sidebar__header__title">App Name</span>
      <span class="app-sidebar__header__icon icon-trailing"></span>

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

      <ul class="app-subnav">
        <li class="app-sidebar__item">
          <a href="#" class="app-sidebar__link">
            <span class="icon icon-leading"><i class="far fa-clipboard"></i></span>
            <span class="app-sidebar__link__text">Relatórios</span>
            <span class="icon icon-trailing">
              <span class="icon-trailing__item-status">
                <i class="fas fa-chevron-down"></i>
              </span>
            </span>
          </a>
        </li>

        <li class="app-sidebar__item">
          <a href="#" class="app-sidebar__link">
            <span class="icon icon-leading"><i class="fas fa-sliders-h"></i></span>
            <span class="app-sidebar__link__text">Configurações</span>
            <span class="icon icon-trailing">
              <span class="icon-trailing__item-status">
                <i class="fas fa-chevron-down"></i>
              </span>
            </span>
          </a>
        </li>

        <li class="app-sidebar__item">
          <a href="#" class="app-sidebar__link">
            <span class="icon icon-leading"><i class="fas fa-file-invoice-dollar"></i></span>
            <span class="app-sidebar__link__text">Gestor de Solicitações</span>
            <span class="icon icon-trailing">
              <span class="icon-trailing__item-status">
                <i class="fas fa-chevron-down"></i>
              </span>
            </span>
          </a>
        </li>

        <li class="app-sidebar__item">
          <a href="#" class="app-sidebar__link">
            <span class="icon icon-leading"><i class="fas fa-list-ol"></i></span>
            <span class="app-sidebar__link__text">Gestão Almoxarifado</span>
            <span class="icon icon-trailing">
              <span class="icon-trailing__item-status">
                <i class="fas fa-chevron-down"></i>
              </span>
            </span>
          </a>
        </li>

        <li class="app-sidebar__item">
          <a href="#" class="app-sidebar__link">
            <span class="icon icon-leading"><i class="far fa-money-bill-alt"></i></span>
            <span class="app-sidebar__link__text">Grupo Espécie</span>
            <span class="icon icon-trailing">
              <span class="icon-trailing__item-status">
                <i class="fas fa-chevron-down"></i>
              </span>
            </span>
          </a>
        </li>

        <li class="app-sidebar__item">
          <a href="#" class="app-sidebar__link">
            <span class="icon icon-leading"><i class="fas fa-globe-americas"></i></span>
            <span class="app-sidebar__link__text">Solicitação</span>
            <span class="icon icon-trailing">
              <span class="icon-trailing__item-status">
                <i class="fas fa-chevron-down"></i>
              </span>
            </span>
          </a>
        </li>
      </ul>
    </li>

    <li class="app-sidebar__item">
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

      <ul class="app-subnav">
        <li class="app-sidebar__item">
          <a href="#" class="app-sidebar__link">
            <span class="icon icon-leading"><i class="far fa-clipboard"></i></span>
            <span class="app-sidebar__link__text">Relatórios</span>
            <span class="icon icon-trailing">
              <span class="icon-trailing__item-status">
                <i class="fas fa-chevron-down"></i>
              </span>
            </span>
          </a>
        </li>

        <li class="app-sidebar__item">
          <a href="#" class="app-sidebar__link">
            <span class="icon icon-leading"><i class="fas fa-sliders-h"></i></span>
            <span class="app-sidebar__link__text">Avaliação Patrimonial</span>
            <span class="icon icon-trailing">
              <span class="icon-trailing__item-status">
                <i class="fas fa-chevron-down"></i>
              </span>
            </span>
          </a>
        </li>

        <li class="app-sidebar__item">
          <a href="#" class="app-sidebar__link">
            <span class="icon icon-leading"><i class="fas fa-file-invoice-dollar"></i></span>
            <span class="app-sidebar__link__text">Configurações</span>
            <span class="icon icon-trailing">
              <span class="icon-trailing__item-status">
                <i class="fas fa-chevron-down"></i>
              </span>
            </span>
          </a>
        </li>

        <li class="app-sidebar__item">
          <a href="#" class="app-sidebar__link">
            <span class="icon icon-leading"><i class="fas fa-list-ol"></i></span>
            <span class="app-sidebar__link__text">Contas Patrimoniais</span>
            <span class="icon icon-trailing">
              <span class="icon-trailing__item-status">
                <i class="fas fa-chevron-down"></i>
              </span>
            </span>
          </a>
        </li>

        <li class="app-sidebar__item">
          <a href="#" class="app-sidebar__link">
            <span class="icon icon-leading"><i class="far fa-money-bill-alt"></i></span>
            <span class="app-sidebar__link__text">Gestor de Inventários</span>
            <span class="icon icon-trailing">
              <span class="icon-trailing__item-status">
                <i class="fas fa-chevron-down"></i>
              </span>
            </span>
          </a>
        </li>

        <li class="app-sidebar__item">
          <a href="#" class="app-sidebar__link">
            <span class="icon icon-leading"><i class="fas fa-globe-americas"></i></span>
            <span class="app-sidebar__link__text">Gestão Patrimonial</span>
            <span class="icon icon-trailing">
              <span class="icon-trailing__item-status">
                <i class="fas fa-chevron-down"></i>
              </span>
            </span>
          </a>
        </li>

        <li class="app-sidebar__item">
          <a href="#" class="app-sidebar__link">
            <span class="icon icon-leading"><i class="fas fa-globe-americas"></i></span>
            <span class="app-sidebar__link__text">Grupo Espécie</span>
            <span class="icon icon-trailing">
              <span class="icon-trailing__item-status">
                <i class="fas fa-chevron-down"></i>
              </span>
            </span>
          </a>
        </li>

        <li class="app-sidebar__item">
          <a href="#" class="app-sidebar__link">
            <span class="icon icon-leading"><i class="fas fa-globe-americas"></i></span>
            <span class="app-sidebar__link__text">Localizações Patrimoniais</span>
            <span class="icon icon-trailing">
              <span class="icon-trailing__item-status">
                <i class="fas fa-chevron-down"></i>
              </span>
            </span>
          </a>
        </li>

        <li class="app-sidebar__item">
          <a href="#" class="app-sidebar__link">
            <span class="icon icon-leading"><i class="fas fa-globe-americas"></i></span>
            <span class="app-sidebar__link__text">Sequência Patrimonial</span>
            <span class="icon icon-trailing">
              <span class="icon-trailing__item-status">
                <i class="fas fa-chevron-down"></i>
              </span>
            </span>
          </a>
        </li>

        <li class="app-sidebar__item">
          <a href="#" class="app-sidebar__link">
            <span class="icon icon-leading"><i class="fas fa-globe-americas"></i></span>
            <span class="app-sidebar__link__text">Tabela de Avaliação</span>
            <span class="icon icon-trailing">
              <span class="icon-trailing__item-status">
                <i class="fas fa-chevron-down"></i>
              </span>
            </span>
          </a>
        </li>
      </ul>
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

    <div class="app-sidebar__footer">
      <li class="app-sidebar__divider"></li>

      <ul class="app-sidebar__footer__nav">
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
</template>

<script>
export default {
  name: 'AppSidebar',

  mounted() {
    const appSidebarToggle = this.$refs['app-sidebar__hide']
    appSidebarToggle.addEventListener('click', () => {
      document.body.classList.remove('app-sidebar--show')
      document.body.classList.add('app-sidebar--hide-desktop')
    })
    
    const appSidebarToggleShrink = this.$refs['app-sidebar__toggle-shrink']
    appSidebarToggleShrink.addEventListener('click', () => {
      document.body.classList.toggle('app-sidebar--shrink')
    })

    const appSubnavs = document.querySelectorAll('.app-subnav')
    appSubnavs.forEach(appSubnav => {
      const appSidebarItem = appSubnav.closest('.app-sidebar__item')
      const appSidebarLink = appSidebarItem.querySelector('.app-sidebar__link')

      appSidebarLink.addEventListener('click', () => {
        document.querySelectorAll('.app-sidebar__item--expand').forEach(el => {
          if (el !== appSidebarItem) {
            el.classList.remove('app-sidebar__item--expand')
          }
        })

        appSidebarItem.classList.toggle('app-sidebar__item--expand')
      })
    })
  }
}
</script>

<style lang="scss">
:root {
  --app-sidebar-background-color: #112cd3;
  --app-sidebar-width: 80%;
  --app-sidebar-icon-font-size: 1.2rem;
  --app-sidebar-icon-width: 2rem;
  --app-sidebar-divider-color: rgba(44, 44, 44, .45);
  --app-sidebar-transition-timing: .4s;
}

.app-sidebar {
  background-color: var(--app-sidebar-background-color, #112cd3);
  // border: 1px solid coral; // debug
  position: fixed;
  top: 0;
  left: 0;
  height: 100%;
  transition: var(--app-sidebar-transition-timing, -4s) cubic-bezier(0.165, 0.84, 0.44, 1);
  transform: translateX(-100%);
  box-shadow: 0 1px 1px rgba(0,0,0,0.15),
              0 2px 2px rgba(0,0,0,0.15),
              0 4px 4px rgba(0,0,0,0.15),
              0 8px 8px rgba(0,0,0,0.15);
  overflow: auto;
  width: var(--app-sidebar-width);
}

.app-sidebar--show .app-sidebar {
  transform: translateX(0);
}

.app-sidebar--shrink .app-sidebar {
  width: calc(1rem + var(--app-sidebar-icon-width) + .75rem);

  .app-sidebar__header {
    position: relative;

    &__icon:not(.icon-trailing), &__title {
      display: none;
    }
  }
}

.app-sidebar--show.app-sidebar--shrink .app-sidebar {
  &__hide {
    position: absolute;
    left: 0;
    top: 50%;
    transform: translate(calc(50% - .4rem), -50%);
  }
}

.app-sidebar {
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

      &:hover {
        cursor: pointer;
      }
    }
  }

  &__item {
    display: block;
  }

  &__link {
    color: white;
    display: flex;
    align-items: center;
    padding: .85rem 1rem;
    text-decoration: none;
    transition: var(--app-sidebar-transition-timing);

    > * {
      flex: 0 0 auto;
    }

    .icon-leading {
      // border: 1px solid coral; // debug
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
      transition: var(--app-sidebar-transition-timing);
    }
  }

  &__link:not(.app-sidebar__toggle-shrink):hover,
  &__item--expand > &__link:not(.app-sidebar__toggle-shrink) {
    background-color: #040609;
  }

  &__divider {
    border-bottom: 1px solid var(--app-sidebar-divider-color);
    display: block;
  }
}

.app-sidebar .app-subnav {
  border-left: .15rem solid tomato;
  max-height: 0;
  overflow: hidden;
  transition: var(--app-sidebar-transition-timing);
}

.app-sidebar .app-sidebar__item--expand {
  > .app-subnav {
    max-height: 100vh;
  }

  > .app-sidebar__link .icon-trailing {
    &__item-status {
      transform: rotate(180deg);
    }
  }
}

@media screen and (min-width: 450px) {
  :root {
    --app-sidebar-width: 23rem;
  }
}

@media screen and (min-width: 1024px) {
  :root {
    font-size: 16px;
    --app-sidebar-width: 20rem;
  }

  .app-sidebar {
    transform: translateX(0);
  }

  .app-sidebar .app-subnav {
    border-left: .35rem solid #040609;
  }

  .app-sidebar--hide-desktop {
    .app-sidebar {
      box-shadow: none;
      transform: translateX(-100%);
    }
  }

  .app-sidebar--shrink .app-sidebar {
    overflow-x: hidden;
  }
}
</style>
