<template>
  <div class="app">
    <v-card color="red" width="400" class="mb-12">
          <v-tabs
            v-model="tab"
            align-tabs="title"
          >
            <v-tab>
              JavaScript
            </v-tab>
            <v-tab>
              HTML
            </v-tab>
            <v-tab>
              CSS
            </v-tab>
          </v-tabs>
      <v-window v-model="tab">
        <v-window-item>
          <v-card flat color="#b19f9f">
            <v-card-text> a </v-card-text>
          </v-card>
        </v-window-item>
        <v-window-item>
          <v-card flat color="green">
            <v-card-text> b </v-card-text>
          </v-card>
        </v-window-item>
        <v-window-item>
          <v-card flat color="yellow">
            <v-card-text> c </v-card-text>
          </v-card>
        </v-window-item>
      </v-window>
    </v-card>

    <button style="font-size: 1em; cursor:pointer; background: red;" @click="scrollToElement">Scroll to Element with No Offset</button>

    <!-- Carousel !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!! -->
    <v-carousel show-arrows="hover" cycle interval="3500" touch>
    <v-carousel-item
      src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
      cover
    ></v-carousel-item>
    <v-carousel-item
      src="https://cdn.vuetifyjs.com/images/cards/hotel.jpg"
      cover
    ></v-carousel-item>
    <v-carousel-item
      src="https://cdn.vuetifyjs.com/images/cards/sunshine.jpg"
      cover
    ></v-carousel-item>
    </v-carousel>


    <!-- HAHA !!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!! -->

    <v-row>
    <v-col
      cols="12"
      sm="6"
    >
      <v-hover
        v-slot="{ isHovering, props }"
        open-delay="200"
      >
        <v-card
          :elevation="isHovering ? 16 : 2"
          :class="{ 'on-hover': isHovering }"
          class="mx-auto"
          height="350"
          max-width="350"
          v-bind="props"
        >
          <v-card-text class="font-weight-medium mt-12 text-center text-subtitle-1">
            Open Delay (Mouse enter)
          </v-card-text>
        </v-card>
      </v-hover>
    </v-col>

    <v-col
      cols="12"
      sm="6"
    >
      <v-hover
        v-slot="{ isHovering, props }"
        close-delay="200"
      >
        <v-card
          :elevation="isHovering ? 16 : 2"
          :class="{ 'on-hover': isHovering }"
          class="mx-auto"
          height="350"
          max-width="350"
          v-bind="props"
        >
        <v-img
          :aspect-ratio="16/9"
          cover
          src="https://cdn.vuetifyjs.com/images/cards/kitchen.png"
        >
          <v-expand-transition>
            <div
              v-if="isHovering"
              class="d-flex transition-fast-in-fast-out bg-orange-darken-2 v-card--reveal text-h2"
              style="height: 100%;"
            >
              $14.99
            </div>
          </v-expand-transition>
        </v-img>
          <v-card-text class="font-weight-medium mt-12 text-center text-subtitle-1">
            Close Delay (Mouse leave)
          </v-card-text>
        </v-card>
      </v-hover>
    </v-col>
  </v-row>



  <div class="text-center">
    <v-progress-circular
      :size="50"
      color="primary"
      indeterminate
    ></v-progress-circular>

    <v-progress-circular
      :width="3"
      color="red"
      indeterminate
    ></v-progress-circular>

    <v-progress-circular
      :size="70"
      :width="7"
      color="purple"
      indeterminate
    ></v-progress-circular>

    <v-progress-circular
      :width="3"
      color="green"
      indeterminate
    ></v-progress-circular>

    <v-progress-circular
      :size="50"
      color="amber"
      indeterminate
      ref="element"
    ></v-progress-circular>
  </div>

        <v-color-picker v-model="buttonColor"></v-color-picker>
        <v-btn
        append-icon="mdi-language-javascript"
        class="ma-2 btn-js"
        :color="buttonColor"

      >
        Accept
      </v-btn>



    <v-text-field label="Label" append-inner-icon="mdi-language-javascript"></v-text-field>

  <v-row>
    <v-col
      cols="12"
      sm="6"
    >
      <v-hover
        v-slot="{ isHovering, props }"
        open-delay="200"
        close-delay="2000"
      >
        <v-card
          :elevation="isHovering ? 16 : 2"
          :class="{ 'on-hover': isHovering }"
          :color="isHovering ? 'primary' : undefined"
          class="mx-auto"
          height="350"
          max-width="350"
          v-bind="props"
        >
          <v-card-text class="font-weight-medium mt-12 text-center text-subtitle-1">
            Open Delay (Mouse enter)
          </v-card-text>
        </v-card>
      </v-hover>
    </v-col>
  </v-row>
  <div class="espaco"></div>
  <div class="espaco"></div>
  <div class="espaco"></div>
  <h1 ref="element">Element You Want To Scroll To</h1>
  <div class="espaco"></div>


  </div>


</template>

<script>
  export default {
    data () {
      return {
        buttonColor: "",
        el: "#app",
        tab: null,
        items: [
          'web', 'shopping', 'videos', 'images', 'news',
        ],
        text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
      }
    },
    methods: {
      scrollToElement() {
        this.$refs["element"].scrollIntoView({ behavior: "smooth" });
    },
      scrollToHiddenElement() {
        this.$refs["hiddenElement"].scrollIntoView({ behavior: "smooth" });
    }
  }
  }
</script>

<style scoped>
  .changecolor {
    background-color: blue;
  }

/*   .btn-js {
    color: yellow !important;
  }
 */
 .app {
    background-color: grey;
  }

  .espaco {
    height: 500px;
    width: 500px;
  }

</style>
