<template>
  <div>
    <v-container fill-height>
      <v-layout
        justify-center
        align-center
        wrap
      >
        <v-flex xs12 mb-5>
          <alpha-card-feature :features="cardFeatures" />
        </v-flex>
        <v-flex xs12 mb-3>
          <h2>{{ $t('Views.Home.testimonialsTitle') }}</h2>
        </v-flex>
        <v-flex
          xs12
          sm6
          v-for="(testimonial, i) in testimonials.slice(0,2)"
          :key="i"
        >
          <alpha-testimonial
            :author="testimonial.author"
            :title="testimonial.title"
            :quote="testimonial.quote"
          />
        </v-flex>
      </v-layout>
    </v-container>

    <alpha-hero
      src="/static/home-parallax.png"
      :height="$vuetify.breakpoint.mdAndUp ? 500 : 'auto'"
      :jumbotron="false"
      dark
      class="mt-5"
    >
      <v-container
        fill-height
        grid-list-xl
      >
        <v-layout
          align-center
          justify-space-around
          wrap
        >
          <v-flex
            xs10
            md6
          >
            <alpha-testimonial
              :author="testimonials[2].author"
              :title="testimonials[2].title"
              :quote="testimonials[2].quote"
            />
          </v-flex>
        </v-layout>
      </v-container>
    </alpha-hero>
  </div>
</template>

<script>
  export default {
    metaInfo: {
      title: 'Vuetify Alpha',
      meta: [
        { name: 'description', content: 'Customized vue-cli templates for Vue and Vuetify' }
      ]
    },
    computed: {
      cardFeatures () {
        return this.$t('Views.Home.cardFeatures')
      },
      testimonials () {
        return this.$t('Views.Home.testimonials')
      }
    }
  }
</script>
