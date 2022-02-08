<template>
  <div>
    <p>Hello world</p>

    <v-container>
      <v-row justify="space-around">
        <v-card width="1000" elevation="0">
          <v-img
            height="200px"
            src="https://cdn.pixabay.com/photo/2020/07/12/07/47/bee-5396362_1280.jpg"
          >
            <v-app-bar flat color="rgba(0, 0, 0, 0)"> </v-app-bar>

            <v-card-title class="white--text mt-8">
              <v-spacer></v-spacer>
              <v-fab-transition>
                <v-btn fab small bottom right class="mt-8">
                  <v-icon>mdi-instagram</v-icon>
                </v-btn>
              </v-fab-transition>
              <!-- <p class="ml-3">John Doe</p> -->
            </v-card-title>
          </v-img>

          <v-card-text style="position: relative">
            <v-fab-transition>
              <v-btn
                v-show="!hidden"
                color="pink"
                dark
                absolute
                top
                fab
                style="left: 50%; transform: translateX(-50%)"
              >
                <v-avatar size="120" style="border: 5px solid white">
                  <img
                    alt="user"
                    src="https://cdn.pixabay.com/photo/2020/06/24/19/12/cabbage-5337431_1280.jpg"
                  />
                </v-avatar>
              </v-btn>
            </v-fab-transition>

            <v-card-title
              style="justify-content: center"
              class="black--text mt-8"
            >
              Lavisha Arora
            </v-card-title>

            <p class="text-center font-weight-bold">
              Professional Makeup artist and educator
            </p>

            <p class="black--text text-center font-weight-black">
              98 <span class="font-weight-regular"> Followers </span>
            </p>
            <v-layout justify-center>
              <v-card-actions>
                <v-btn outlined width="150">
                  <span>Follow</span>
                </v-btn>
              </v-card-actions>
            </v-layout>
            <v-container fluid class="pt-10">
              <v-row dense>
                <v-col
                  v-for="card in cards"
                  :key="card.title"
                  :cols="card.flex"
                >
                  <v-card class="rounded-xl">
                    <v-img
                      :src="card.src"
                      class="white--text align-end"
                      gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                      height="300px"
                    >
                      <v-fab-transition>
                        <v-btn
                          class="rounded-md"
                          v-show="!hidden"
                          color="white lighten-1"
                          x-small
                          absolute
                          top
                          right
                          depressed
                        >
                          0.00
                        </v-btn>
                      </v-fab-transition>
                    </v-img>
                  </v-card>
                </v-col>
              </v-row>
            </v-container>
          </v-card-text>
        </v-card>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  name: 'Card',

  data() {
    return {
      cards: [
        {
          title: 'Pre-fab homes',
          src: 'https://cdn.vuetifyjs.com/images/cards/house.jpg',
          flex: 3,
        },
        {
          title: 'Favorite road trips',
          src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg',
          flex: 3,
        },
        {
          title: 'Best airlines',
          src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg',
          flex: 3,
        },
        {
          title: 'Best airlines',
          src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg',
          flex: 3,
        },
        {
          title: 'Pre-fab homes',
          src: 'https://cdn.vuetifyjs.com/images/cards/house.jpg',
          flex: 3,
        },
        {
          title: 'Favorite road trips',
          src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg',
          flex: 3,
        },
        {
          title: 'Best airlines',
          src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg',
          flex: 3,
        },
        {
          title: 'Best airlines',
          src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg',
          flex: 3,
        },
      ],
    };
  },
  methods: {},
};
</script>
