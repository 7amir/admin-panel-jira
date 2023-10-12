<script>
export default {

}
</script>

<template>
  <header>
    <v-container>
      <v-row>
        <v-col class="header-list d-flex align-center pr-0" cols="8">
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

        <v-col cols="4" class="header-icons d-flex justify-end align-center pl-0" align="left">
          <div class="search-box ml-2">
            <v-card width="200">
              <v-text-field
                density="compact"
                variant="solo"
                label="جستجو"
                append-inner-icon="mdi-magnify"
                single-line
                hide-details
              ></v-text-field>
            </v-card>
          </div>
          
          <v-btn>
            <v-icon>mdi-bell</v-icon>
          </v-btn>

          <v-btn>
            <v-icon>mdi-help-circle</v-icon>
          </v-btn>

          <v-btn>
            <v-icon>mdi-cog</v-icon>
          </v-btn>

          <div class="admin-icon mr-2">
            <span>AR</span>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </header>
</template>


<style lang="scss" scoped>
header {
  position: relative;
  // box-shadow: 0px 2px 10px -7px #6a6a6a;
  // overflow-y: hidden;



  &::after {
    height: var(--ds-space-050, 4px);
    position: absolute;
    top: 100%;
    right: 0px;
    left: 0px;
    background: linear-gradient(rgba(9, 30, 66, 0.13) 0px, rgba(9, 30, 66, 0.13) 1px, rgba(9, 30, 66, 0.08) 1px, rgba(9, 30, 66, 0) 4px);
    content: ""
  }
}
</style>