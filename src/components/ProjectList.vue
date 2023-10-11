<script>
export default {
  data() {
    return {
      items: [
        {
          title: 'برنامه ریزی',
          disabled: false,
          href: 'breadcrumbs_link_1',
        },
        {
          title: 'هیئت مدیره',
          disabled: false,
          href: 'breadcrumbs_link_2',
        },
      ],
      tab: null,
    }
  }

}
</script>

<template>
  <v-container class="project-title">
    <v-breadcrumbs :items="items"></v-breadcrumbs>
    <h6>هیئت مدیره</h6>

    <!-- <v-tabs v-model="tab">
      <v-tab value="one">Item One</v-tab>
      <v-tab value="two">Item Two</v-tab>
      <v-tab value="three">Item Three</v-tab>
    </v-tabs>

    <v-card-text>
      <v-window v-model="tab">
        <v-window-item value="one"> One </v-window-item>

        <v-window-item value="two"> Two </v-window-item>

        <v-window-item value="three"> Three </v-window-item>
      </v-window>
    </v-card-text> -->
  </v-container>
</template>


<style lang="scss" scoped>
.project-title {
  h6 {
    font-size: 20px;
  }
}
</style>