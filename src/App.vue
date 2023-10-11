<script>
import Header from './components/Header.vue';
import SlideBar from './components/SlideBar.vue';
import ProjectList from './components/ProjectList.vue';

export default {
  components: { Header, SlideBar, ProjectList }
}
</script>

<template>
  <v-locale-provider rtl>
    <Header />
    <SlideBar />
    <ProjectList />

  </v-locale-provider>
</template>

<style lang="scss" scoped></style>