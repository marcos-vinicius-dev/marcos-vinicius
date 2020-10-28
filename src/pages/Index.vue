<template lang="pug">
  div(class="row justify-center")
    div(class="col-10 col-md-8")
      div(class="row q-col-gutter-xl q-pt-xl")
        div(class="col-12 col-lg-6")
          div(class="row")
            div(class="col-12 col-md-10")
              div(class="text-h2 text-weight-bold text-white")
                | Hello, I’m
                <br>
                | Marcos Vinicius.
              div(class="text-white q-mt-md")
                | Graduated in Analysis and Systems Development. I currently work as a vue.js senior developer. I mostly do front-end development, where I work on strategic innovation projects. I have great experience in JavaScript, Node.js, Vue.js and Graphql. I'm a javascript enthusiast, a fan of vue.js, passionate about clean code and good practices. I'm always interested in acquiring new knowledge and I love solving new challenges.

          div(class="row q-pt-lg q-col-gutter-md")
            div
              q-btn(
                no-caps
                unelevated
                class="text-weight-medium"
                color="primary"
                href="https://github.com/marcos-vinicius-dev"
                label="Github"
                target="_blank"
                type="a"
                :icon-right="require('@quasar/extras/mdi-v5').mdiGithub"
              )
            div
              q-btn(
                no-caps
                unelevated
                class="text-weight-medium"
                color="primary"
                href="https://www.linkedin.com/in/marcos-vinicius-35a054154/"
                label="Linkedin"
                target="_blank"
                type="a"
                :icon-right="require('@quasar/extras/mdi-v5').mdiLinkedin"
              )

        div(class="col-12 col-lg-6")
          div(class="text-h5 text-weight-bold text-white q-mb-md")
            | Github
          div(class="row q-col-gutter-sm group")
            div(
              class="col-12 col-md-6"
              v-for="(repo, index) in repositores"
              :key="`lg-${index}`"
            )
              q-card(
                flat
                dark
                class="full-width bg-primary q-pa-lg cursor-pointer transition card:group-hover:opacity-50 card:hover:opacity-important card:hover:scale-11/10x"
              )
                q-card-section
                  div(class="full-width text-overline text-uppercase")
                    | {{ repo.technology }}
                  div(class="full-width text-h5 text-weight-medium")
                    | {{ repo.name }}
                  div(class="full-width q-mt-sm")
                    | {{ repo.description }}

        div(class="col-12 q-mt-xl")
          div(class="text-h5 text-weight-bold text-white q-mb-md")
            | Skills
          div(class="row q-col-gutter-sm q-mb-md")
            div(
              class="col-12 col-md-2"
              v-for="(repo, index) in skills"
              :key="`lg-${index}`"
            )
              q-card(
                dark
                flat
                class="full-width bg-primary q-pa-lg"
              )
                q-icon(
                  size="50px"
                  :name="repo.img"
                  :style="`color: ${repo.colorIcon};`"
                )

                q-card-section
                  div(class="full-width text-h6 text-weight-medium")
                    | {{ repo.technology }}

        div(class="col-12 q-mt-xl")
          div(class="text-h5 text-weight-bold text-white q-mb-md")
            | Portfolio
          div(class="row q-col-gutter-md group q-mb-md")
            div(
              class="col-12 col-md-3"
              v-for="(port, index) in portfolio"
              :key="`lg-${index}`"
            )
              q-card(
                flat
                class="opacity bg-primary cursor-pointer"
              )
                q-img(
                  basic
                  :src="port.img"
                )
                q-card-section
                  div(class="full-width text-h6 text-weight-medium text-white")
                    | {{ port.name }}
                  div(class="full-width text-overline text-uppercase text-grey-7")
                    | {{ port.company }}

</template>

<script>
export default {
  name: 'PageIndex',

  data () {
    return {
      repositores: [
        {
          name: 'Vue.Pic',
          description: 'Creating a SPA (Single Page Application) in the form of a photo management program. ',
          technology: 'Vue.js'
        },
        {
          name: 'NODE API',
          description: 'REST API to manage products and product categories. Using Nodej, Express and Sequelize',
          technology: 'Node.js'
        },
        {
          name: 'Pay Fast',
          description: 'Payment rest api made on nodejs',
          technology: 'Node.js'
        },
        {
          name: 'JavaScript ES6+ for Beginners',
          description: 'ES6 Javascript for beginners, with javascript examples and exercises to do and their answers.',
          technology: 'JavaScript'
        }
      ],
      skills: [
        {
          img: require('@quasar/extras/mdi-v5').mdiLanguageJavascript,
          colorIcon: '#f0db4f',
          technology: 'JavaScript'
        },
        {
          img: require('@quasar/extras/mdi-v5').mdiVuejs,
          colorIcon: '#41b883',
          technology: 'Vue.js'
        },
        {
          img: require('@quasar/extras/mdi-v5').mdiNodejs,
          colorIcon: '#87c042',
          technology: 'Node.js'
        },
        {
          img: require('@quasar/extras/mdi-v5').mdiGraphql,
          colorIcon: '#e535ab',
          technology: 'Graphql'
        },
        {
          img: require('@quasar/extras/mdi-v5').mdiLanguageHtml5,
          colorIcon: '#f67b35',
          technology: 'Html'
        },
        {
          img: require('@quasar/extras/mdi-v5').mdiLanguageCss3,
          colorIcon: '#2ab8e6',
          technology: 'Css'
        }
      ],
      portfolio: [
        {
          name: 'Direito à cidadania',
          url: '',
          img: '../statics/direito.jpg',
          company: 'Marcos Vinicius'
        },
        {
          name: 'Realmente fácil',
          url: '',
          img: '../statics/realmente-facil.jpg',
          company: 'Infinite Cloud'
        },
        {
          name: 'Ibyte',
          url: '',
          img: '../statics/ibyte.jpg',
          company: 'Bis2Bis E-commerce'
        },
        {
          name: 'Parceiro Dj Movéis',
          url: '',
          img: '../statics/dj-moveis.jpg',
          company: 'Bis2Bis E-commerce'
        }
      ]
    }
  }
}
</script>

<style>
.opacity .q-img {
  opacity: 0.7;
}

.opacity:hover .q-img {
  opacity: 1;
}
.group:hover .card\:group-hover\:opacity-50 {
    opacity: .1;
}

.card\:hover\:opacity-important:hover {
    opacity: 1!important;
}

.transition {
    transition-property: background-color,border-color,color,fill,stroke,opacity,box-shadow,transform;
    transition: all .2s ease-in-out;
}

.group-2:hover .card\:group-2-hover\:scale-11\/10x, .card\:hover\:scale-11\/10x:hover {
    transform: scale(1.1);
}

</style>
