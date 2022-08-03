<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <h1 
    :style="colorContador">{{ titulo }}: {{ contador }}</h1>
    <!-- <button @click="incrementar">Aumentar</button>
    <BtnDisminuir /> -->
    <hr>
    <BotonAccion :estado="true" />
    <BotonAccion :estado="false" />
  </div>
</template>

<script>
import { mapState, mapMutations, mapActions } from 'vuex'
import BtnDisminuir from './../components/BtnDisminuir'
import BotonAccion from './../components/BotonAccion'


export default {
  name: 'HomeView',
  components: {
    BtnDisminuir, BotonAccion
  },
  data() {
    return {
      titulo: 'Mi contador Vuex'
    }
  },
  computed: {
    ...mapState(['contador']),
    colorContador(){
      return [this.contador >= 100 ? {'color': 'green'} : {'color': 'red'}]
    }
  },
  methods:{
    ...mapMutations(['incrementar']),
    ...mapActions(['accionIncrementar']),
    // ...mapMutations(['decrementar']),
    // ...mapActions(['accionDecrementar'])
  }
}
</script>
