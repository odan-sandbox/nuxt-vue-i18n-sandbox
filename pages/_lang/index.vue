<template>
  <div>
    <p>
      {{ $t("hello") }}
    </p>
    <button @click="changeLang">change to {{otherLang}}</button>
  </div>
</template>

<script>
export default {
  computed: {
    otherLang() {
      return this.$i18n.locale == 'ja' ? 'en' : 'ja';
    }
  },
  methods: {
    changeLang() {
      const router = this.$router;
      this.$store.dispatch('changeLang', { router, lang: this.otherLang })
    }
  }
}
</script>
