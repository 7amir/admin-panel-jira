<script>
export default {
  data() {
    return {
      admin: [
        { title: 'مدیریت کابر', icon: 'mdi-account-group' },
        { title: 'صدور صورت حساب', icon: 'mdi-newspaper-variant-outline' },
      ],
      adminSetting: [
        { title: 'سیستم', icon: 'mdi-laptop' },
        { title: 'محصولات', icon: 'mdi-basket-outline' },
      ],
      drawer: null,
    }
  }
}
</script>

<template>
  <header>
    <v-container>
      <v-row>
        <v-col lg="8" md="8" sm="9" class="header-list d-flex align-center pr-0">
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

              <v-list-item class="hidden-md-and-down d-md-block">
                <a href="#">فیلترها
                  <v-icon size="small">mdi-chevron-down</v-icon>
                </a>
              </v-list-item>

              <v-list-item class="hidden-md-and-down d-md-block">
                <a href="#">داشبوردها
                  <v-icon size="small">mdi-chevron-down</v-icon>
                </a>
              </v-list-item>

              <v-list-item class="hidden-lg-and-down d-lg-block">
                <a href="#">تیم‌ها
                  <v-icon size="small">mdi-chevron-down</v-icon>
                </a>
              </v-list-item>

              <v-list-item class="hidden-lg-and-down d-lg-block">
                <a href="#">برنامه‌ها
                  <v-icon size="small">mdi-chevron-down</v-icon>
                </a>
              </v-list-item>

              <v-list-item class=" hidden-lg">
                <a href="#">بیشتر
                  <v-icon size="small">mdi-chevron-down</v-icon>
                </a>
              </v-list-item>

              <v-btn color="#0052CC" class="mr-2 hidden-lg-and-down d-lg-block">ایجاد</v-btn>

              <v-btn color="#0052CC" class="mr-2 pr-0 pl-0 hidden-lg" min-width="32">
                <v-icon>mdi-plus</v-icon>
              </v-btn>
            </v-list>
          </div>
        </v-col>

        <v-col 
          lg="4" 
          md="4" 
          sm="3" 
          class="header-icons d-flex justify-end  align-center pl-0">
          <div class="search-box ml-2">
            <v-card 
              width="200" 
              class="hidden-lg-and-down d-lg-block d-md-block"
              >
              <v-text-field 
                density="compact" 
                variant="solo" 
                label="جستجو" append-inner-icon="mdi-magnify" 
                single-line
                hide-details>
              </v-text-field>
            </v-card>

            <v-card width="32" height="32" class="search-responsive justify-center align-center">
              <v-icon>mdi-magnify</v-icon>
            </v-card>
          </div>

          <v-btn class="hidden-lg-and-down d-lg-block">
            <v-icon>mdi-bell</v-icon>
          </v-btn>

          <!-- <v-btn class="hidden-lg-and-down d-lg-block">
            <v-icon>mdi-help-circle</v-icon>
          </v-btn> -->

          <!-- کمک -->
          <v-locale-provider ltr>
            <v-layout>
              <v-navigation-drawer v-model="drawer" temporary>
                <v-list-item
                  prepend-avatar="https://randomuser.me/api/portraits/men/78.jpg"
                  title="John Leider"
                ></v-list-item>
  
                <v-divider></v-divider>
  
                <v-list density="compact" nav>
                  <v-list-item
                    prepend-icon="mdi-view-dashboard"
                    title="Home"
                    value="home"
                  ></v-list-item>
                  <v-list-item
                    prepend-icon="mdi-forum"
                    title="About"
                    value="about"
                  ></v-list-item>
                </v-list>
              </v-navigation-drawer>

                <v-btn
                  class="hidden-lg-and-down d-lg-block"
                  @click.stop="drawer = !drawer"
                  >
                  <v-icon>mdi-help-circle</v-icon>
                </v-btn>

            </v-layout> 
          </v-locale-provider>

          <!-- تنظیمات -->
          <v-menu>
            <template v-slot:activator="{ props }">
              <v-btn class="hidden-lg-and-down d-lg-block" v-bind="props">
                <v-icon>mdi-cog</v-icon>
              </v-btn>
            </template>

            <v-list class="list-cog shadow">
              <v-list-item>
                <h6>تنظیمات</h6>
              </v-list-item>

              <v-list-item class="item-title">ادمین جیرا</v-list-item>

              <v-list-item 
                v-for="(item, index) in admin" 
                :key="index" 
                :value="index"
                >
                <template v-slot:prepend>
                  <v-icon :icon="item.icon"></v-icon>
                </template>
                <v-list-item-title>{{ item.title }}</v-list-item-title>
    
              </v-list-item>

              <v-list-item class="item-title">تنظیمات ادمین پنل</v-list-item>
              <v-list-item 
                v-for="(item, index) in adminSetting" 
                :key="index" :value="index"
                >
                <template v-slot:prepend>
                  <v-icon :icon="item.icon"></v-icon>
                </template>
                <v-list-item-title>{{ item.title }}</v-list-item-title>
              </v-list-item>

            </v-list>
          </v-menu>

          <!-- ادمین -->
          <v-menu>
            <template v-slot:activator="{ props }">
              <div class="admin-icon mr-2" v-bind="props">
                <span>AR</span>
              </div>
            </template>

            <v-list class="list-account shadow pt-1 pb-1">
              <v-list-item class="pb-0">
                <v-list-item-title>حساب</v-list-item-title>
              </v-list-item>

              <div class="d-flex mr-3 mt-1 mb-1">
                <div class="admin-icon">
                  <span>AR</span>
                </div>
                <div class="account-info mr-2 ml-5">
                  <p>امیر رجب زاده</p>
                  <span>amir.rj@gmail.com</span>
                </div>
              </div>

              <v-list-item value="account">
                <div class="d-flex justify-space-between">
                  <p>مدیریت حساب</p>
                  <v-icon>mdi-exit-to-app</v-icon>
                </div>
              </v-list-item>

              <v-divider class="mb-1 mt-1"></v-divider>

              <v-list-item>
                <v-list-item-title>ادمین پنل</v-list-item-title>
              </v-list-item>

              <v-list-item value="profile">
                پروفایل
              </v-list-item>

              <v-list-item value="cog">
                تنظیمات شخصی
              </v-list-item>

              <v-list-item value="them">
                تم
              </v-list-item>

              <v-divider class="mb-1"></v-divider>

              <v-list-item value="exit">
                خروج از حساب
              </v-list-item>
            </v-list>
          </v-menu>
        </v-col>
      </v-row>
    </v-container>
  </header>
</template>


<style lang="scss" scoped>
header {
  position: fixed;
  width: 100%;
  z-index: 1;
  background: #fff;

  &::after {
    height: 4px;
    position: absolute;
    top: 100%;
    right: 0px;
    left: 0px;
    background: linear-gradient(rgba(9, 30, 66, 0.13) 0px, rgba(9, 30, 66, 0.13) 1px, rgba(9, 30, 66, 0.08) 1px, rgba(9, 30, 66, 0) 4px);
    content: ""
  }

}

.account-info {
  font-family: Vazir-regular;

  span {
    font-family: Vazir-light;
  }
}

h6 {
  font-size: 16px;
}
</style>