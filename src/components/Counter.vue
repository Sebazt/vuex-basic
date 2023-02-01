<template>
  <h1>Counter - vuex</h1>
  <h2>Direct Acces: {{ $store.state.count }}</h2>
   <h2>Computed: {{ countComputed }}</h2>

  <button @click="increment">Increment +1 </button>
  <button @click="incrementBy">Increment +5 </button>
  <button @click="incrementRandomInt">Random </button>
  <h1>Map State</h1>
  <h2>MapState: {{ count }}</h2>
</template>

<script>
import { mapState } from 'vuex';

export default {

  computed: {
    countComputed() {
      return this.$store.state.count;
    },
    ...mapState({
      count: state => state.count
    })
  },

  methods:{
    increment(){
      this.$store.commit('increment')
    },
    incrementBy(){
      this.$store.commit('incrementBy', 5)
    },
    incrementRandomInt(){
      this.$store.dispatch('incrementRandomInt')
    }
  }
};
</script>
