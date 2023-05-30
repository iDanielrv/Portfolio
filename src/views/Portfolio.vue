<template>

    <v-app class="app">
      <v-app-bar color="#1f1e1b" dense fixed>
        <v-spacer></v-spacer>
        <v-tabs v-model="tab" color="#FF8303" align-tabs="center" bg-color="#1f1e1b" class="mr-12">
          <v-tab :value="1" class="menuButton mr-5" @click="scrollToElement1" >Sobre</v-tab>
          <v-tab :value="2" class="menuButton mr-5" @click="scrollToElement2">Skills</v-tab>
          <v-tab :value="3" class="menuButton mr-5" @click="scrollToElement3">Repositorio</v-tab>
          <v-tab :value="4" class="menuButton mr-5" @click="scrollToElement4">Cursos</v-tab>

        </v-tabs>
      </v-app-bar>

      <v-row no-gutters class="d-flex justify-space-around align-center">
        <div class="hello d-flex align-center">
          <div style="width: 40vw">
            <h1 style="font-size: 64px">Daniel Ripper Vitorino</h1>
            <h2>Programador</h2>
            <p>Programador Web Full Stack</p>
          </div>
        </div>
        <div>
          <img src="@/assets/img/logo_background.svg" alt="" style="height: 500px;">
        </div>

      </v-row>
          <br ref="sobre">
          <v-divider :thickness="3" class="mb-12"></v-divider>
        <div class="mb-12">
          <v-row no-gutters>
            <v-col cols="2" class="d-flex justify-center">
              <img src="@/assets/img/logo_background.svg" alt="">
            </v-col>
            <v-col cols="6" class="d-flex justify-center">
              <v-card variant="tonal" class="myJourney pa-12">
                <h2>Sobre mim</h2>
                Olá! Como estudante de Ciência da Computação, estou em busca de uma empresa que me proporcione um ambiente de aprendizado e permita colocar em prática os conhecimentos adquiridos em cursos e na universidade. Tenho habilidades em Desenvolvimento Web e grande interesse em Desenvolvimento Mobile, e estou animado para contribuir em empresas nestas áreas.
              </v-card>
            </v-col>

          </v-row>
        </div>
          <br ref="skills">
          <v-divider :thickness="3"></v-divider>
        <div>
          <h2 class="text-center my-12">Skills</h2>

          <v-row no-gutters class="mb-12 d-flex justify-center">
            <v-card
              height="130"
              width="150"
              variant="tonal"
              class="mx-12 pa-4 cardTest d-text justify-center align-center"
            >
              <div class="skillCardText">
                <h3>Html</h3>
                <v-icon size="64" class="cardIcon d-flex align-center">mdi-language-html5</v-icon>
              </div>
            </v-card>

            <v-card
              height="130"
              width="150"
              variant="tonal"
              class="mx-12 pa-4 cardTest d-text justify-center align-center"
            >
              <div class="skillCardText">
                <h3>Css</h3>
                <v-icon size="64" class="cardIcon d-flex align-center">mdi-language-css3</v-icon>
              </div>
            </v-card>

            <v-card
              height="130"
              width="150"
              variant="tonal"
              class="mx-12 pa-4 cardTest d-text justify-center align-center"
            >
              <div class="skillCardText">
                <h3>JavaScript</h3>
                <v-icon size="64" class="cardIcon d-flex align-center">mdi-language-javascript</v-icon>
              </div>
            </v-card>

            <v-card
              height="130"
              width="150"
              variant="tonal"
              class="mx-12 pa-4 cardTest d-text justify-center align-center"
            >
              <div class="skillCardText">
                <h3>Node</h3>
                <v-icon size="64" class="cardIcon d-flex align-center">mdi-nodejs</v-icon>
              </div>
            </v-card>

            <v-card
              height="130"
              width="150"
              variant="tonal"
              class="mx-12 pa-4 cardTest d-text justify-center align-center"
            >
              <div class="skillCardText">
                <h3>Vue js</h3>
                <v-icon size="64" class="cardIcon d-flex align-center">mdi-vuejs</v-icon>
              </div>
            </v-card>

          </v-row>
        </div>
        <v-divider :thickness="3"></v-divider>
        <br  ref="repositorio">
        <div>
          <h2 class="text-center my-12">Meus Projetos</h2>

              <v-card
    class="mx-auto mb-16 github"
    max-width="344"
    variant="tonal"
  >
    <v-img
      src="https://cdn-icons-png.flaticon.com/512/25/25231.png"
      height="200px"
      cover
    ></v-img>

    <br>
    <v-card-title >
      GitHub
    </v-card-title>

    <v-card-subtitle>
      Repositorio:
    </v-card-subtitle>

    <v-card-actions>
      <v-btn variant="tonal" :href="githubLink" target="_blank">
        Explorar!
      </v-btn>

      <v-spacer></v-spacer>

      <v-btn
        :icon="show ? 'mdi-chevron-up' : 'mdi-chevron-down'"
        @click="show = !show"
      ></v-btn>
    </v-card-actions>

    <v-expand-transition>
      <div v-show="show">
        <v-divider></v-divider>

        <v-card-text>
          No meu repositório no GitHub, adiciono projetos que me interessam e oferecem aprendizado durante a programação. Procuro diversificar nas áreas, como aplicações web, aprendizado de máquina e jogos. Contribuo para projetos de código aberto, compartilho meus projetos no GitHub e valorizo o feedback da comunidade de desenvolvedores. Além disso, documento o código e forneço instruções claras.
        </v-card-text>
      </div>
    </v-expand-transition>
  </v-card>


        </div>

        <v-divider :thickness="3"></v-divider>
        <br id="cursos">

        <div>
          <h2 class="text-center my-12" ref="cursos">Cursos</h2>
          <h3 class="mb-12 text-center">Alguns dos cursos que eu fiz:</h3>


          <div class="cursosImg ">
            <v-carousel
              class="mb-16"
              cycle
              height="300"
              max-width="444"
              show-arrows="hover"
            >
              <v-carousel-item
                src="../../public/javascript.png"
                cover
              ></v-carousel-item>

              <v-carousel-item
                src="../../public/node.png"
                cover
              ></v-carousel-item>

              <v-carousel-item
                src="../../public/udemy.png"
                cover
              ></v-carousel-item>
            </v-carousel>
          </div>
        </div>

        <v-divider :thickness="3"></v-divider>
        <v-footer
      class="bg-indigo-lighten-1 text-center d-flex flex-column footer"
    >
      <div>
        <v-btn
          v-for="icon in icons"
          :key="icon"
          class="mx-4"
          :icon="icon.icon"
          variant="text"
          :href="icon.link"
          target="_blank"
        ></v-btn>
      </div>

      <div class="pt-0">
        Criado com carinho!
      </div>

      <v-divider></v-divider>

      <div>
        {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
      </div>
    </v-footer>


    </v-app>


</template>

<script>
  export default {
    data: () => ({
      tab: null,
      icons: [
        {
          icon: 'mdi-facebook',
          link: 'http://www.facebook.com'
        },
        {
          icon: 'mdi-twitter',
          link: 'http://www.twitter.com'
        },
        {
          icon: 'mdi-linkedin',
          link: 'http://www.linkedin.com'
        },
        {
          icon: 'mdi-instagram',
          link: 'http://www.instagram.com'
        },
      ],
      show: false,
      githubLink: 'https://github.com/iDanielrv',
    }),
      methods: {
        scrollToElement1() {
          this.$refs["sobre"].scrollIntoView({ behavior: "smooth" });
        },
        scrollToElement2() {
          this.$refs["skills"].scrollIntoView({ behavior: "smooth" });
        },
        scrollToElement3() {
          this.$refs["repositorio"].scrollIntoView({ behavior: "smooth" });
        },
        scrollToElement4() {
          this.$refs["cursos"].scrollIntoView({ behavior: "smooth" });
        },
        scrollToHiddenElement() {
          this.$refs["hiddenElement"].scrollIntoView({ behavior: "smooth" });
        }
      }
  }
</script>

<style scoped>
.app {
    background-color: #1b1a17;
    color: white;
  }
  .app h1,
  .app h2 {
    color: #ff8343;
  }

.menuButton {
  color: white;
}

.algumaCoisa{
  height: 300px;
  width: 300px;
}
.cursosImg {
  width: 800px;
  margin: 0 auto;
}
.myJourney {
  text-align: justify;
}
.hello {
  height: 87vh;
}

.skillCard:hover {
  border-right: 50px solid #373633;
  border-left: 50px solid #373633;
  transition: .6s;
}
.skillCard:not(:hover){
  transition: .3s;
}

.cardTest:hover {
  background: #ff8343;
  transition: .5s;
}

.cardIcon {
  text-align: center;
  margin: auto;
}

.skillCardText {
  justify-items: center;
  text-align: center;
  justify-content: center;
}

.footer {
  background-color: #1F1E1B !important;
}
.github {
  font-size: 16px;
}
a {
  color: white;
  text-decoration: none;
}

</style>
