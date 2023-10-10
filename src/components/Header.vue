<script>
export default {

}
</script>

<template>
  <header>
    <v-container>
      <v-row>
        <v-col class="header-list d-flex align-center" cols="8">
          <div class="menu ml-3">
            <svg xmlns="http://www.w3.org/2000/svg" width="25" height="25" viewBox="0 0 24 24">
              <path fill="currentColor"
                d="M8 6a2 2 0 1 1-4 0a2 2 0 0 1 4 0Zm0 6a2 2 0 1 1-4 0a2 2 0 0 1 4 0Zm-2 8a2 2 0 1 0 0-4a2 2 0 0 0 0 4Zm8-14a2 2 0 1 1-4 0a2 2 0 0 1 4 0Zm-2 8a2 2 0 1 0 0-4a2 2 0 0 0 0 4Zm2 4a2 2 0 1 1-4 0a2 2 0 0 1 4 0Zm4-10a2 2 0 1 0 0-4a2 2 0 0 0 0 4Zm2 4a2 2 0 1 1-4 0a2 2 0 0 1 4 0Zm-2 8a2 2 0 1 0 0-4a2 2 0 0 0 0 4Z" />
            </svg>
          </div>

          <div class="admin-panel ml-4">
            <h3>ادمین پنل</h3>
          </div>

          <div class="menu-list">
            <v-list class="d-flex pt-0 pb-0">
              <v-list-item>
                <a href="#">کار
                  <v-icon size="small">mdi-chevron-down</v-icon>
                </a>
              </v-list-item>

              <v-list-item>
                <a href="#">پروژه‌ها
                  <v-icon size="small">mdi-chevron-down</v-icon>
                </a>
              </v-list-item>

              <v-list-item>
                <a href="#">فیلترها
                  <v-icon size="small">mdi-chevron-down</v-icon>
                </a>
              </v-list-item>

              <v-list-item>
                <a href="#">داشبوردها
                  <v-icon size="small">mdi-chevron-down</v-icon>
                </a>
              </v-list-item>
              <v-list-item>
                <a href="#">تیم‌ها
                  <v-icon size="small">mdi-chevron-down</v-icon>
                </a>
              </v-list-item>
              <v-list-item>
                <a href="#">برنامه‌ها
                  <v-icon size="small">mdi-chevron-down</v-icon>
                </a>
              </v-list-item>

              <v-btn color="#0052CC" class="mr-2">ایجاد</v-btn>
            </v-list>
          </div>
        </v-col>

        <v-col cols="4" class="header-icons" align="left">2</v-col>
      </v-row>
    </v-container>
  </header>
</template>


<style lang="scss" scoped>
</style>