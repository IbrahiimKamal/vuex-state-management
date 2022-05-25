<template>
  <base-container v-if="isAuth" title="Vuex">
    <the-counter></the-counter>
    <favorite-value></favorite-value>
    <button @click="addOne">Add 10</button>
    <change-counter />
  </base-container>
  <base-container title="auth">
    <user-auth></user-auth>
  </base-container>
</template>

<script>
import BaseContainer from './components/BaseContainer.vue';
import ChangeCounter from './components/ChangeCounter.vue';
import FavoriteValue from './components/FavoriteValue.vue';
import TheCounter from './components/TheCounter.vue';
import UserAuth from './components/UserAuth.vue';

export default {
  methods: {
    addOne() {
      // this.$store.commit('increase', { value: 10 });
      this.$store.dispatch({
        type: 'numbers/increment',
        value: 10,
      });
    },
  },

  computed: {
    counter() {
      return this.$store.state.counter;
    },
    isAuth() {
      return this.$store.getters.userIsAuth;
    },
  },

  components: {
    BaseContainer,
    TheCounter,
    ChangeCounter,
    FavoriteValue,
    UserAuth,
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>
