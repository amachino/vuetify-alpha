<template>
  <v-fade-transition mode="out-in">
    <v-jumbotron
      v-if="namespace"
      :key="$route.path"
      :src="heroImage"
      height="40vh"
      gradient="to top, rgba(160, 90, 70, .85), rgba(30, 40, 30, .85)"
    >
      <v-fade-transition mode="out-in">
        <v-container
          fill-height
          :key="$route.path"
          v-if="isBooted"
        >
          <v-layout align-center>
            <v-fade-transition mode="out-in">
              <v-flex
                text-xs-center
                :key="$route.path"
              >
                <h1 class="display-2 white--text" v-html="title" />
                <div
                  class="subheading white--text"
                  v-html="subTitle"
                  v-if="subTitle"
                />
              </v-flex>
            </v-fade-transition>
          </v-layout>
        </v-container>
      </v-fade-transition>
    </v-jumbotron>
  </v-fade-transition>
</template>

<script>
  export default {
    data: () => ({
      isBooted: false
    }),

    computed: {
      isHome () {
        return this.$route.path === '/'
      },
      namespace () {
        return this.$route.name
      },
      title () {
        return this.$t(`Views.${this.namespace}.jumbotronTitle`)
      },
      subTitle () {
        return this.$t(`Views.${this.namespace}.jumbotronSubTitle`)
      },
      heroImage () {
        return `/static/${this.namespace.toLowerCase()}-hero.png`
      }
    },

    mounted () {
      setTimeout(() => {
        this.isBooted = true
      }, 200)
    }
  }
</script>
