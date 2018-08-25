<template>
  <v-toolbar
    app
    dark
    :flat="!isScrolling"
    :color="!isScrolling ? 'transparent' : 'secondary'"
    v-scroll="onScroll"
  >
    <img
      src="/static/alpha-construction-logo.png"

    />
    <v-spacer />
    <v-toolbar-items v-if="$vuetify.breakpoint.mdAndUp">
      <v-btn
        v-for="(item, i) in items"
        :active-class="!isScrolling ? 'primary--text' : undefined"
        :key="i"
        :to="item.to"
        flat
      >
        <span v-text="item.text" />
      </v-btn>
    </v-toolbar-items>
    <v-btn v-else icon @click="toggleDrawer">
      <v-icon>mdi-menu</v-icon>
    </v-btn>
  </v-toolbar>
</template>

<script>
  // Utilities
  import { mapMutations } from 'vuex'

  export default {
    data: () => ({
      isScrolling: false
    }),

    computed: {
      items () {
        return this.$t('Layout.View.items')
      }
    },

    methods: {
      ...mapMutations('app', ['toggleDrawer']),
      onScroll () {
        this.isScrolling = (window.pageYOffset ||
          document.documentElement.scrollTop || 0) > 100
      }
    }
  }
</script>
