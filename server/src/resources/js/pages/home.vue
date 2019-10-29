<template>
  <section>
    <div class="alert alert-info" role="alert">
      A simple light alert—check it out!
    </div>
    <card :title="$t('home')">
      {{ $t('you_are_logged_in') }}
    </card>
  </section>
</template>

<script>
export default {
  middleware: 'auth',

  metaInfo () {
    return { title: this.$t('home') }
  }
}
</script>
