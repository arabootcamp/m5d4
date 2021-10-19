<template>
  <div class="pt-5">
    <p v-if="personaje==null" class="text-center">No hay personaje a mostrar.</p>
    <v-container v-else>
      <v-card elevation="2" max-width="300" class="mx-auto">
        <v-img height="300" :src="personaje.imagen" :alt="personaje.nombre"></v-img>
        <v-card-title>{{personaje.nombre}}</v-card-title>
        <v-card-text>Otra cosa que se podria añadir para dar más detalles del personaje</v-card-text>
      </v-card>
    </v-container>
  </div>
</template>

<script>
  export default {
    computed: {
      personaje() {
        let personajes = this.$store.getters['getPersonajes'];
        const found = personajes.find((el) => {
          if (el.id == this.$route.params.id)
            return el;
        });
        return found;
      }
    }
  }

</script>
