<template>
  <button @click="inc">Add 2</button>
  <button @click="increase({ value: 10 })">Add 10</button>
</template>

<script>
import { mapActions } from 'vuex';

export default {
  methods: {
    // addOne() {
    // this.$store.dispatch('increase', { value: 2 });
    // },
    // ...mapActions(['increase', 'increment']),
    ...mapActions({
      inc: 'increment',
      increase: 'increase',
    }),
  },
};
</script>
