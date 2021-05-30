<template>
  <v-card outlined>
    <!--encabezado-->
    <v-card-title  >
      <v-list-item >

        <v-list-item-content>
          <v-list-item-title class="title">Cliente</v-list-item-title>
          <v-list-item-subtitle class="subtitle-1"> <small>Lista</small> </v-list-item-subtitle>
        </v-list-item-content>

        <v-spacer></v-spacer>
        <v-icon x-large>mdi-account</v-icon>
      </v-list-item>
    </v-card-title>
    <v-divider></v-divider>
    <!--fin encabezado-->

    <!-- contenido-->
    <v-card-text>
      <template>
        <v-row>
          <v-spacer></v-spacer>
          <v-col cols="12" xs="12" sm="7" align="right">
            <v-btn color="primary" dark class="mb-2" @click="openForm(true)">
              <v-icon left>mdi-plus</v-icon>
              Nuevo cliente
            </v-btn>
          </v-col>
        </v-row>

      </template>

      <clientes-form
          :is-new="isNew"
          :dialog="dialog"
          @close="close"
      ></clientes-form>


      <clientes-table

          @openForm="openForm"

      ></clientes-table>
    </v-card-text>
  </v-card>
</template>

<script>
import ClientesTable from "./table";
import {mapState} from "vuex";
// import axios from 'axios';
import ClientesForm from "./form";
export default {
  name: "clientes-index",
  components: {ClientesForm, ClientesTable},
  data: () => ({
    dialog: false,
    isNew: true,
  }),
  mounted() {

  },
  methods: {
    close() {
      this.dialog = false;
    },
    openForm(isNew, id = 0) {
      this.dialog = true;
      this.isNew = isNew;
      console.log(id);
    },


  },
  computed: {
    ...mapState(['url_base'])
  }
}
</script>

<style scoped>

</style>