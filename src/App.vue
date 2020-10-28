<template>
  <v-app>
    <v-app-bar app color="dark" dark>
      <h1 text-center>Rick and Morty</h1>
      <v-spacer></v-spacer>
    </v-app-bar>

    <v-main>
      <template>
        <v-container>
          <v-row justify="start">
            <!-- recorriendo el arreglo de personaje -->
            <v-col
              md="4"
              v-for="(personaje, i) in personajes"
              :key="i"
              class="pensando"
            >
              <v-card>
                <v-img :src="personaje.imagen" height="200px"></v-img>
                <!-- doble moustach -->
                <v-card-title> {{ personaje.nombre }} </v-card-title>

                <v-card-actions>
                    <v-spacer></v-spacer>

                    <v-btn icon @click="personaje.show = !personaje.show">
                        <v-icon>{{personaje.show ? "mdi-chevron-up" : "mdi-chevron-down"}}</v-icon>
                        </v-btn>
                </v-card-actions>

                <v-expand-transition>
                  <div v-show="personaje.show">
                    <v-divider></v-divider>

                    <v-card-text>
                      I'm a thing. But, like most politicians, he promised more
                      than he could deliver. You won't have time for sleeping,
                      soldier, not with all the bed making you'll be doing. Then
                      we'll go with that data file! Hey, you add a one and two
                      zeros to that or we walk! You're going to do his laundry?
                      I've got to find a way to escape.
                    </v-card-text>
                  </div>
                </v-expand-transition>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </template></v-main
    ></v-app
  >
</template>


<script>
import HelloWorld from "./components/HelloWorld";

export default {
  name: "App",

  components: {
    HelloWorld,
  },

  data: () => ({
    //personajes ingresados de desafiolatam
    personajes: [
      {
        id: 1,
        nombre: "Morty",
        imagen: "https://rickandmortyapi.com/api/character/avatar/2.jpeg",
        show: false,
      },
      {
        id: 2,
        nombre: "Rick",
        imagen: "https://rickandmortyapi.com/api/character/avatar/1.jpeg",
        show: false,
      },
      {
        id: 3,
        nombre: "Summer",
        imagen: "https://rickandmortyapi.com/api/character/avatar/3.jpeg",
        show: false,
      },
      {
        id: 4,
        nombre: "Beth",
        imagen: "https://rickandmortyapi.com/api/character/avatar/4.jpeg",
        show: false,
      },
      {
        id: 5,
        nombre: "Jerry",
        imagen: "https://rickandmortyapi.com/api/character/avatar/5.jpeg",
        show: false,
      },
    ],
  }),
};
</script>

<style scoped>
.pensando {
  padding: 0px;
}
</style>
