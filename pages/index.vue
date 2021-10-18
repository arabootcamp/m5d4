<template>
  <div>
    <v-container>
      <v-row>
        <v-col cols="12" sm="6" md="4" v-for="el in personajes" :key="el.id">
          <v-card elevation="2" max-width="300" class="mx-auto">
            <v-img height="300" :src="el.imagen" :alt="el.nombre"></v-img>
            <v-card-title>{{el.nombre}}</v-card-title>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
  import {
    defineComponent
  } from '@vue/composition-api'

  export default {
    name: 'index',
    computed: {
      personajes() {
        return this.$store.getters['getPersonajes'];
      }
    }
  }

</script>
