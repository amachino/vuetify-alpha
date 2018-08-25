<template>
  <alpha-footer
    :company="$t('Layout.Footer.company')"
    :social="social"
    :categories="categories"
  >
    <span>
      &copy; 2017
      {{ $t('Layout.Footer.company') }}
      &mdash;
      {{ $t('Layout.Footer.rights') }}
    </span>
  </alpha-footer>
</template>

<script>
  export default {
    computed: {
      social () {
        return this.$t('Layout.Footer.social')
      },
      categories () {
        return this.$t('Layout.Footer.categories')
      }
    }
  }
</script>
