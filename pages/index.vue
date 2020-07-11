<template>
  <div>
    <v-layout column align-center>
      <v-avatar size="200">
        <img src="~/static/ahoussou.png" alt="ahoussou" />
      </v-avatar>
      <span> DEVELOPPEUR WEB </span>
    </v-layout>
    <v-divider></v-divider>
    <h2 class="green--text">PROFILE</h2>
    <v-container fluid>
      <v-card class="mx-auto" max-width="1200" outlined>
        <v-list-item three-line>
          <v-list-item-content>
            <v-card-text class="profile text-justify">
              Je suis un jeune developpeur passionné de web depuis mes premières
              années universtaires, pour moi le web est comme une feuille vierge
              où le développeur (l'artisant) laisse parler son imagination et sa
              créativité d'où le concept de page web et de material design. Je
              m'intéresse plus précisement dans le web aux nouvelles
              technologies et aux cadres de dévéloppement modernes . Le regard
              tourné toujours vers le futur et à ce qu'il peut nous apporté de
              meilleur, je m'adapte continuellement aux nouveaux outils
              disponibles et pour plus de flexibilité je privilegie les outils
              cross-platforme.
            </v-card-text>
          </v-list-item-content>
        </v-list-item>
      </v-card>
    </v-container>
    <v-divider></v-divider>
    <h2 class="green--text">PARCOURS ACADEMIQUE</h2>
    <v-container fluid>
      <v-card class="mx-auto" max-width="1200" outlined>
        <v-list-item three-line>
          <v-list-item-content>
            <v-card-text>
              <v-timeline align-top flat>
                <v-timeline-item
                  v-for="(item, i) in items"
                  :key="i"
                  :color="item.color"
                  :icon="item.icon"
                  fill-dot
                >
                  <span slot="opposite"
                    ><h3>{{ item.interval }}</h3></span
                  >
                  <v-card :color="item.color" dark>
                    <v-card-title class="title">{{ item.text }}</v-card-title>
                  </v-card>
                </v-timeline-item>
              </v-timeline>
            </v-card-text>
          </v-list-item-content>
        </v-list-item>
      </v-card>
    </v-container>
    <v-divider></v-divider>
    <h2 class="green--text">COMPETENCES</h2>
    <v-container fluid>
      <v-card class="mx-auto" max-width="1200" outlined>
        <v-list-item three-line>
          <v-list-item-content>
            <v-card-text>
              <v-row align="center" class="spacer" no-gutters>
                <v-col cols="3">
                  <v-list flat>
                    <v-subheader><h2>SGBD</h2></v-subheader>
                    <v-list-item-group color="black">
                      <v-list-item
                        v-for="(competence, cs) in competences.sgbd.content"
                        :key="cs"
                      >
                        <v-list-item-icon>
                          <v-img
                            :src="competence.avatar"
                            width="45"
                            height="45"
                            alt="avatar 1"
                          ></v-img>
                        </v-list-item-icon>
                        <v-list-item-content>
                          <v-list-item-title
                            v-text="competence.name"
                          ></v-list-item-title>
                        </v-list-item-content>
                      </v-list-item>
                    </v-list-item-group>
                  </v-list>
                </v-col>
                <v-col cols="3">
                  <v-list flat>
                    <v-subheader><h2>Java-Script</h2></v-subheader>
                    <v-list-item-group color="black">
                      <v-list-item
                        v-for="(competence, cj) in competences.js.content"
                        :key="cj"
                      >
                        <v-list-item-icon>
                          <v-img
                            :src="competence.avatar"
                            height="35"
                            width="45"
                            alt="avatar 1"
                          ></v-img>
                        </v-list-item-icon>
                        <v-list-item-content>
                          <v-list-item-title
                            v-text="competence.name"
                          ></v-list-item-title>
                        </v-list-item-content>
                      </v-list-item>
                    </v-list-item-group>
                  </v-list>
                </v-col>
                <v-col cols="3">
                  <v-list flat>
                    <v-subheader><h2>PHP</h2></v-subheader>
                    <v-list-item-group color="black">
                      <v-list-item
                        v-for="(competence, cp) in competences.php.content"
                        :key="cp"
                      >
                        <v-list-item-icon>
                          <v-img
                            :src="competence.avatar"
                            width="45"
                            height="45"
                            alt="avatar 1"
                          ></v-img>
                        </v-list-item-icon>
                        <v-list-item-content>
                          <v-list-item-title
                            v-text="competence.name"
                          ></v-list-item-title>
                        </v-list-item-content>
                      </v-list-item>
                    </v-list-item-group>
                  </v-list>
                </v-col>
                <v-col cols="3">
                  <v-list flat>
                    <v-subheader><h2>Devops</h2></v-subheader>
                    <v-list-item-group color="black">
                      <v-list-item
                        v-for="(competence, cd) in competences.devops.content"
                        :key="cd"
                      >
                        <v-list-item-icon>
                          <v-img
                            :src="competence.avatar"
                            width="35"
                            height="35"
                            alt="avatar 1"
                          ></v-img>
                        </v-list-item-icon>
                        <v-list-item-content>
                          <v-list-item-title
                            v-text="competence.name"
                          ></v-list-item-title>
                        </v-list-item-content>
                      </v-list-item>
                    </v-list-item-group>
                  </v-list>
                </v-col>
              </v-row>
            </v-card-text>
          </v-list-item-content>
        </v-list-item>
      </v-card>
    </v-container>
    <v-divider></v-divider>
    <h2 class="green--text">
      REALISATIONS
    </h2>
    <v-container fluid>
      <v-alert
        class="mx-auto realisation text-justify"
        max-width="1200"
        text
        prominent
        color="deep-orange"
        icon="mdi-fire"
      >
        Pas grand chose pour l'instant. donnez moi l'occasion de réaliser
        quelque chose avec vous !!
      </v-alert>
    </v-container>
  </div>
</template>

<script>
export default {
  head: {
    title: 'AHOUSSOU JEAN-CHRIS ARNAUD🚀',
    meta: [
      {
        hid: 'curriculum',
        name: 'compétences',
        content: 'Developpement web fullstack'
      }
    ],
    noscript: [{ innerHTML: 'Body No Scripts', body: true }],
    script: [
      { src: '/head.js' },
      // Supported since 1.0
      { src: '/body.js', body: true },
      { src: '/defer.js', defer: '' }
    ]
  },
  data: () => ({
    items: [
      {
        color: 'orange darken-1',
        icon: 'mdi-numeric-3',
        interval: '2018-2020',
        text: 'Master Génie Informatique et logiciel'
      },
      {
        color: 'red darken-1',
        icon: 'mdi-numeric-2',
        interval: '2012-2018',
        text: 'Licence Informatique Générale'
      },
      {
        color: 'blue darken-1',
        icon: 'mdi-numeric-1',
        interval: '2011-2012',
        text: 'Baccalauréat Scientifique'
      }
    ],
    competences: {
      php: {
        avatar: 'https://cdn.worldvectorlogo.com/logos/php.svg',
        content: [
          {
            avatar:
              'https://upload-icon.s3.us-east-2.amazonaws.com/uploads/icons/png/15754208491553750212-512.png',
            name: 'Laravel',
            percent: 70
          },
          {
            avatar:
              'https://cdn.freebiesupply.com/logos/thumbs/2x/lumen-1-logo.png',
            name: 'Lumen',
            percent: 20
          }
        ]
      },
      js: {
        avatar: 'https://cdn.worldvectorlogo.com/logos/es6.svg',
        content: [
          {
            avatar:
              'https://seeklogo.com/images/V/vuejs-logo-17D586B587-seeklogo.com.png',
            name: 'Vuejs',
            percent: 50
          },
          {
            avatar:
              'https://seeklogo.com/images/N/nuxt-logo-5EF50E1ABD-seeklogo.com.png',
            name: 'Nuxtjs',
            percent: 50
          },
          {
            avatar: 'https://getdrawings.com/free-icon/lua-icon-64.png',
            name: 'Expressjs',
            percent: 50
          }
        ]
      },
      devops: {
        avatar:
          'https://previews.123rf.com/images/vectorhome/vectorhome1907/vectorhome190700579/127615654-devops-icon-vector.jpg',
        content: [
          {
            avatar: 'https://cdn.worldvectorlogo.com/logos/tux.svg',
            name: 'Linux OS',
            percent: 50
          },
          {
            avatar: 'https://cdn.worldvectorlogo.com/logos/git-icon.svg',
            name: 'github',
            percent: 50
          }
        ]
      },
      sgbd: {
        avatar: '',
        content: [
          {
            avatar:
              'https://www.clipartmax.com/png/middle/33-338445_open-source-vector-images-postgresql-logo.png',
            name: 'Postgresql',
            percent: 20
          },
          {
            avatar:
              'https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcTnJ8aqG9sKeAfZ0saMcAAQDqSqkafZuSfCAg&usqp=CAU',
            name: 'Oracle',
            percent: 20
          },
          {
            avatar:
              'https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcQo2-sIH4MvLI2VvwHHwDiPsXxQTu8f8d7QIw&usqp=CAU',
            name: 'MySQL-MariaDB',
            percent: 70
          }
        ]
      }
    }
  })
}
</script>
<style lang="css" scoped>
.profile {
  font-size: 20px;
}
.realisation {
  font-size: 20px;
}
</style>
