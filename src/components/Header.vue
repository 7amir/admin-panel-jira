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
      items: [
        { type: 'subheader', title: 'امروز' },
        {
          prependAvatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg',
          title: 'برانچ این آخر هفته',
          subtitle: `<span class="text-primary">علی مرادی</span> &mdash; من این آخر هفته در محله شما خواهم بود و کارها را انجام می دهم. میخوای بگردی؟`,
        },
        { type: 'divider', inset: true },
        {
          prependAvatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg',
          title: 'باربیکیو تابستانی',
          subtitle: `<span class="text-primary">رضا ندایی</span> &mdash; کاش می توانستم بیایم، اما این آخر هفته خارج از شهر هستم`,
        },
        { type: 'divider', inset: true },
        {
          prependAvatar: 'https://cdn.vuetifyjs.com/images/lists/3.jpg',
          title: 'سفر به پاریس',
          subtitle:
            '<span class="text-primary">پارمیدا حاتمی</span> &mdash; آیا توصیه های پاریس دارید؟ آیا تا به حال بوده اید؟',
        },
      ],
      drawer: null,
      drawerNotification: null,
      dialog: false,
    }
  }
}
</script>

<template>
  <header>
    <v-container>
      <v-row>
        <v-col
          lg="8"
           md="8"
          sm="9"
          class="header-list d-flex align-center pr-0"

          >
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


              <v-dialog v-model="dialog" persistent width="1020" class="dialog-create">
                <template v-slot:activator="{ props }">
                  <v-btn color="#0052CC" v-bind="props" class="mr-2 hidden-lg-and-down d-lg-block">ایجاد</v-btn>
                  <v-btn color="#0052CC" v-bind="props" class="mr-2 pr-0 pl-0 hidden-lg" min-width="32">
                    <v-icon>mdi-plus</v-icon>
                  </v-btn>
                </template>
                <v-card>
                  <v-card-title>
                    <span >ایجاد پروژه</span>
                  </v-card-title>
                  <v-container class="mt-2 mb-4">
                    <v-row>
                      <v-col cols="12" sm="6">
                        <label>نام</label>
                        <v-text-field variant="solo" hide-details="auto"></v-text-field>
                      </v-col>
                      <v-col cols="12" sm="6">
                        <label>پروژه</label>
                        <v-text-field variant="solo" hide-details="auto"></v-text-field>
                      </v-col>

                      <v-col cols="12" sm="6">
                        <label>سن</label>
                        <v-select
                          :items="['0-17', '18-29', '30-54', '54+']"
                          variant="solo"
                          hide-details="auto"
                        ></v-select>
                      </v-col>
                      <v-col cols="12" sm="6">
                        <label>نقش</label>
                        <v-select
                          :items="['مدیر', 'نویسنده', 'مشترک', 'مشارکت کننده']"
                          variant="solo"
                          hide-details="auto"
                        ></v-select>
                      </v-col>

                      <v-col cols="12">
                        <label>توضیح</label>
                        <v-textarea 
                          variant="solo"
                          hide-details="auto">
                        </v-textarea>
                      </v-col>
                    </v-row>
                  </v-container>
                  <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn color="blue-darken-1" variant="text" @click="dialog = false">
                      انصراف
                    </v-btn>
                    <v-btn color="blue-darken-1" variant="text" @click="dialog = false">
                      ذخیره
                    </v-btn>
                  </v-card-actions>
                </v-card>
              </v-dialog>
            </v-list>
          </div>
        </v-col>

        <v-col
          lg="4"
          md="4"
          sm="3"
          class="header-icons d-flex justify-end align-center pl-0"
          >
          <div class="search-box ml-2">
            <v-card 
              width="200" 
              class="hidden-lg-and-down d-lg-block d-md-block">
              <v-text-field 
                density="compact"
                variant="solo"
                label="جستجو"
                append-inner-icon="mdi-magnify"
                single-line
                hide-details>
              </v-text-field>
            </v-card>

            <v-card 
              width="32" 
              height="32" 
              class="search-responsive justify-center align-center">
              <v-icon>mdi-magnify</v-icon>
            </v-card>
          </div>

          <!-- اعلان‌ها -->
          <v-locale-provider ltr>
            <v-layout class="help-box-navigation notification-box">
              <v-navigation-drawer 
                v-model="drawer" 
                temporary 
                class="shadow">
                <v-list-item class="title-setting">
                  <div class="title d-flex justify-space-between pt-1 pb-1 align-center">
                    <v-list-item-title>
                      <h6>اعلان‌ها</h6>
                    </v-list-item-title>
                    <v-btn 
                      variant="text" 
                      @click.stop="drawer = !drawer" 
                      icon="mdi-close" 
                      size="31">
                    </v-btn>
                  </div>
                </v-list-item>

                <v-divider></v-divider>

                <v-list 
                    :items="items" 
                    item-props lines="three" 
                    class="notification">
                  <template v-slot:subtitle="{ subtitle }">
                    <div v-html="subtitle"></div>
                  </template>
                </v-list>

              </v-navigation-drawer>
              <v-btn 
                class="hidden-lg-and-down d-lg-block" 
                @click.stop="drawer = !drawer">
                <v-icon>mdi-bell</v-icon>
              </v-btn>
            </v-layout>
          </v-locale-provider>

          <!-- راهنما -->
          <v-locale-provider ltr>
            <v-layout class="help-box-navigation">
              <v-navigation-drawer 
                v-model="drawerNotification"
                temporary
                class="shadow navigation-help">
                <v-list-item class="title-setting">
                  <div class="title d-flex justify-space-between pt-1 pb-1 align-center">
                    <v-list-item-title>
                      <h6>راهنما</h6>
                    </v-list-item-title>

                    <v-btn 
                      variant="text" 
                      size="31" 
                      class="ml-0 mr-0"
                      @click.stop="drawerNotification = !drawerNotification" 
                      icon="mdi-close">
                    </v-btn>
                  </div>

                </v-list-item>
                <div class="search-box justify-center d-flex mt-1">
                  <v-card width="300">
                    <v-text-field 
                      density="compact"
                      variant="solo"
                      label="مقاله راهنمای جستجو"
                      append-inner-icon="mdi-magnify"
                      single-line hide-details>
                    </v-text-field>
                  </v-card>
                </div>

                <v-divider class="mt-5 mb-4"></v-divider>
                <div class="cards-view">
                  <a href="#" class="link__card-view mb-2">
                    <div class="card-title mb-2">
                      مشاهده و ویرایش مجوزهای نقش پروژه
                    </div>
                    <div class="card-description">
                      از نقش‌های پروژه برای مرتبط کردن افراد و
                      گروه ها با یک پروژه یا محدود کردن
                      دسترسی کاربران یا گروه استفاده کنید.
                    </div>
                  </a>

                  <a href="#" class="link__card-view mb-2">
                    <div class="card-title mb-2">
                      از میانبرهای صفحه کلید استفاده کنید
                    </div>
                    <div class="card-description">
                      سرعت ویرایش، پیمایش و انجام اقدامات را بدون
                      برداشتن انگشتان از صفحه کلید افزایش دهید.
                    </div>
                  </a>

                  <a href="#" class="link__card-view mb-2">
                    <div class="card-title mb-2">
                      چگونه در پروژه‌های تحت مدیریت شرکت گردش کار ایجاد کنیم؟
                    </div>
                    <div class="card-description">
                      گردش کار مورد استفاده در یک پروژه
                      تحت مدیریت شرکت را ایجاد،
                      ویرایش کنید یا نحوه رسیدگی به انواع وظایف را اصلاح کنید.
                    </div>
                  </a>
                </div>

              </v-navigation-drawer>

              <v-btn 
                class="hidden-lg-and-down d-lg-block" 
                @click.stop="drawerNotification = !drawerNotification">
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
              <v-list-item class="mt-1">
                <h6>تنظیمات</h6>
              </v-list-item>

              <v-divider class="mt-1 mb-1"></v-divider>

              <v-list-item class="item-title">ادمین جیرا</v-list-item>

              <v-list-item v-for="(item, index) in admin" :key="index" :value="index">
                <template v-slot:prepend>
                  <v-icon :icon="item.icon"></v-icon>
                </template>
                <v-list-item-title>{{ item.title }}</v-list-item-title>

              </v-list-item>

              <v-list-item class="item-title">تنظیمات ادمین پنل</v-list-item>
              <v-list-item v-for="(item, index) in adminSetting" :key="index" :value="index">
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

            <v-list class="list-account shadow pt-1 pb-1 list-cog">
              <v-list-item class="item-title">حساب</v-list-item>

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
                <div class="d-flex justify-space-between align-center">
                  <p>مدیریت حساب</p>
                  <v-icon>mdi-exit-to-app</v-icon>
                </div>
              </v-list-item>

              <v-divider class="mb-1 mt-1"></v-divider>

              <v-list-item class="item-title">ادمین پنل</v-list-item>

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
  position: relative;
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

.cards-view {
  padding: 0 14px;

  .link__card-view {
    font-size: 12.5px;
    padding: 8px;
    border-radius: 5px;

    .card-title {
      font-family: Vazir-medium;
    }

    .card-description {
      font-family: Vazir-light;
    }

    &:hover {
      background: #EBECF0;
    }
  }
}
</style>