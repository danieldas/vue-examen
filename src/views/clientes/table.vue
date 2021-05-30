<template>
  <v-simple-table>
    <template v-slot:default>
      <thead>
      <tr class="grey lighten-5">
        <th>#</th>
        <th>Nombre</th>
        <th>Primer apellido</th>
        <th>Segundo apellido</th>
        <th>Razón social</th>
        <th>Nit</th>
        <th>Celular</th>
        <th></th>
      </tr>
      </thead>
      <tbody>
      <tr >


      </tr>
      </tbody>
    </template>
  </v-simple-table>
</template>

<script>
import {mapState} from "vuex";

export default {
  name: "clientes-table",
  methods: {


  },
  computed: {
    ...mapState(['url_base'])
  }
}
</script>

<style scoped>

</style>