<script>
import Header from './components/Header.vue';

export default {
  components: { Header }
}
</script>

<template>
  <v-locale-provider rtl>
    <Header />
  </v-locale-provider>
</template>

<style lang="scss" scoped></style>