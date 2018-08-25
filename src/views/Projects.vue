<template>
  <v-container fill-height>
    <v-layout justify-center align-center>
      <v-flex xs8 class="mb-5">
        <alpha-gallery
          :categories="categories"
          :projects="projects"
        />
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
  export default {
    metaInfo: {
      title: 'Projects',
      meta: [
        { name: 'description', content: 'Customized vue-cli templates for Vue and Vuetify' }
      ]
    },
    computed: {
      categories () {
        return this.$t('Views.Projects.categories')
      },
      projects () {
        return this.$t('Views.Projects.projects')
      }
    }
  }
</script>
