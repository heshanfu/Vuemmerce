<template>
  <div>
    <nav class="navbar" role="navigation" aria-label="main navigation">
      <div class="navbar-brand">
        <a class="navbar-item" href="/">
          <h1 class="title is-3">Vuemmerce</h1>
        </a>

        <a role="button" class="navbar-burger burger" aria-label="menu" aria-expanded="false" data-target="navbarBasicExample">
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
        </a>
      </div>

      <div class="navbar-start search-wrapper">
        <div class="control has-icons-left has-icons-right">
          <input class="input" type="text" placeholder="Search...">
          <span class="icon is-small is-left">
            <i class="fas fa-search"></i>
          </span>
        </div>
      </div>

      <div class="navbar-end">
        <div class="navbar-item">
          <div class="shopping-cart">
            <i class="fa fa-shopping-cart"></i>
          </div>
          <div class="buttons">
            <a class="button is-primary" @click="showRegistrationModal">
              <strong>Sign up</strong>
            </a>
            <a class="button is-light" @click="showLoginModal">
              Log in
            </a>
          </div>
        </div>
      </div>
    </nav>
    <login-modal-component :isLoginActive.sync="isLoginActive"></login-modal-component>
    <registration-modal-component :isRegistrationActive.sync="isRegistrationActive"></registration-modal-component>
  </div>
</template>

<script>
  import LoginModal from '../modal/Login';
  import RegistrationModal from '../modal/Registration';

  export default {
    name: 'header-component',

    data () {
      return {
        isLoginActive: false,
        isRegistrationActive: false
      }
    },

    components: {
      'login-modal-component': LoginModal,
      'registration-modal-component': RegistrationModal
    },

    methods: {
      showLoginModal () {
        this.isLoginActive = true;
      },
      showRegistrationModal () {
        this.isRegistrationActive = true;
      }
    }
  };
</script>

<style lang="scss" scoped>
  .search-wrapper {
    margin: 8px auto;
    width: 50%;

    .control { width: 100%; }
  }
  .title { color: #fff; }
  .navbar {
    background: rgb(46, 149, 212);
  }
  .shopping-cart {
    position: relative;
    right: 50px;
    color: #fff;
    cursor: pointer;
  }
</style>
