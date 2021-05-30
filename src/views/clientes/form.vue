<template>
  <v-dialog v-model="dialog" persistent max-width="500px">
    <v-card>
      <v-form  ref="form"
      >
        <v-card-title >
          <span class="headline"> Cliente</span>
        </v-card-title>

        <v-card-text>
          <v-container>



          </v-container>
          <v-divider></v-divider>
        </v-card-text>

        <v-card-actions>
          <v-spacer></v-spacer>

          <v-btn type="submit" color="primary" class="pl-4 pr-4" >Guardar

          </v-btn>
          <v-btn color="blue darken-1" outlined @click="close">Cancelar</v-btn>
        </v-card-actions>
      </v-form>

    </v-card>
  </v-dialog>
</template>

<script>
import {mapState} from "vuex";

export default {
  name: "clientes-form",
  props: [
    'isNew',
    'dialog'
  ],
  data: () => ({
  }),

  methods: {
    close() {
      this.$emit('close');
    },

  },
  computed: {
    ...mapState(['url_base'])
  }
}
</script>

<style scoped>

</style>