<template>
  <button @click="accionDecrementar(50)">Disminuir</button>
</template>

<script>
import { mapActions } from 'vuex'

export default {
//     name: 'BtnDisminuir',
// computed: {
//     ...mapState(['contador']),
   
//   },
  methods:{
   
    // ...mapMutations(['decrementar']),
    ...mapActions(['accionDecrementar'])
  }

}
</script>

<style>

</style>