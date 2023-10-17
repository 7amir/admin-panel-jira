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
      menuItems: [
        { title: 'تغییر نام', icon: 'mdi-account-edit-outline' },
        { title: 'اشتراک گذاری', icon: 'mdi-share-variant-outline' },
        { title: 'نمایش در اکسل', icon: 'mdi-table-arrow-right' },
        { title: 'حذف', icon: 'mdi-delete-empty-outline' },
      ],
      subMenuItems: [
        { title: 'حرکت به پایین', icon: 'mdi-cursor-move' },
        { title: 'کپی کردن لینک', icon: 'mdi-link-variant' },
        { title: 'حذف', icon: 'mdi-delete-empty-outline' },
      ],
      upload: [
        { title: 'OneDrive برای کسب و کار', icon: 'mdi-microsoft-onedrive' },
        { title: 'sharePoint', icon: 'mdi-microsoft-sharepoint' },
        { title: 'تنطیمات فایل‌ها', icon: 'mdi-folder-cog-outline' },
      ],
      tab: null,
    }
  },
  methods: {

  }

}
</script>

<template>
  <v-container class="project-title">
    <v-breadcrumbs :items="items"></v-breadcrumbs>
    <h6>هیئت مدیره</h6>

    <v-row class="justify-space-between mt-3">
      <v-col lg="6" md="6" sm="12">
        <div class="head-box d-flex align-center">
          <div class="search-box search-body ml-2">
            <v-card width="185">
              <v-text-field density="compact" variant="solo" label="جستجو" append-inner-icon="mdi-magnify" single-line
                hide-details></v-text-field>
            </v-card>
          </div>

          <div class="admin-icon mr-2">
            <span>AR</span>
          </div>
          <div class="admin-icon icon-add-user mr-2">
            <v-icon>mdi-account-plus</v-icon>
          </div>
        </div>
      </v-col>

      <v-col lg="6" md="6" sm="12" align="left">
        <div class="icon-action">
          <v-menu>
          <template v-slot:activator="{ props }">
            <v-btn v-bind="props">
              <v-icon class="ml-1">mdi-share-variant-outline</v-icon>
              اشتراک گذاری
            </v-btn>
          </template>
          <v-list class="item-share shadow">
            <v-list-item v-for="(item, index) in upload" :key="index" :value="index">
              <v-icon class="ml-2">{{ item.icon }}</v-icon>
              <v-list-item-title class="title-new-btn">{{ item.title }}</v-list-item-title>
            </v-list-item>

            <v-divider class="mt-2"></v-divider>

            <span class="share-description">یک فایل pbix.، rdl. یا xlsx. را در فضای کاری خود آپلود کنید
            </span>
          </v-list>
        </v-menu> 

          <!-- فیلتر -->
          <v-menu>
            <template v-slot:activator="{ props }">
              <v-btn v-bind="props">
                <v-icon class="ml-1">mdi-filter-variant</v-icon>
                فیلتر
              </v-btn>
            </template>
            <v-list class="list__filter shadow">
              <v-list-item>
                <v-icon class="ml-2"> mdi-calendar-range </v-icon>
                <v-list-item-title>کارت ها را سفارشی کنید</v-list-item-title>
              </v-list-item>

              <v-list-item>
                <v-icon class="ml-2"> mdi-calendar-range </v-icon>
                <v-list-item-title>همه ستون ها را گسترش دهید</v-list-item-title>
              </v-list-item>

              <v-list-item>
                <v-icon class="ml-2"> mdi-calendar-range </v-icon>
                <v-list-item-title>همه ستون ها را جمع کنید</v-list-item-title>
              </v-list-item>

            </v-list>
          </v-menu>

          <v-btn>
            <v-icon class="ml-1">mdi-dots-horizontal</v-icon>
            بیشتر
          </v-btn>
        </div>
      </v-col>
    </v-row>


    <v-row>
      <v-col lg="3" md="6" sm="12">
        <div class="todo-title d-flex justify-space-between align-center">
          <div class="title-text">
            <span>انجام کار</span>
            <span class="mr-2">3</span>
          </div>

          <v-menu class="test-menus">
            <template v-slot:activator="{ props }">
              <v-btn min-width="40" class="pr-0 pl-0 icon-menu-item" v-bind="props">
                <v-icon size="x-large">mdi-dots-horizontal</v-icon>
              </v-btn>
            </template>
            <v-list class="shadow list-todo-box">
              <v-list-item v-for="(item, index) in menuItems" :key="index" :value="index">
                <template v-slot:prepend>
                  <v-icon :icon="item.icon"></v-icon>
                </template>
                <v-list-item-title>{{ item.title }}</v-list-item-title>
              </v-list-item>
            </v-list>
          </v-menu>
        </div>

        <div class="todo-lists">
          <div class="todo-list">
            <div class="title d-flex justify-space-between">
              <span>یاد گرفتن vue</span>

              <v-menu class="test-menus">
                <template v-slot:activator="{ props }">
                  <v-btn min-width="40" class="pr-0 pl-0 icon-menu-item sub-menu-item" v-bind="props">
                    <v-icon size="x-large">mdi-dots-horizontal</v-icon>
                  </v-btn>
                </template>
                <v-list class="shadow list-todo-box">
                  <v-list-item v-for="(item, index) in subMenuItems" :key="index" :value="index">
                    <template v-slot:prepend>
                      <v-icon :icon="item.icon"></v-icon>
                    </template>
                    <v-list-item-title>{{ item.title }}</v-list-item-title>
                  </v-list-item>
                </v-list>
              </v-menu>

            </div>
            <div class="todo-check mt-7 d-flex justify-space-between">
              <div class="input-check d-flex align-center">
                <input type="checkbox" class="ml-2">
                <span class="task-details">قسمت 1</span>
              </div>

              <div class="icons">
                <v-btn min-width="5" max-height="18" class="pr-0 pl-0">
                  <v-icon color="green">mdi-check</v-icon>
                  <v-tooltip location="bottom" activator="parent">انجام شده</v-tooltip>
                </v-btn>
                <v-icon color="orange" class="mr-2">mdi-chevron-double-up</v-icon>
              </div>
            </div>
          </div>
          <div class="todo-list">
            <div class="title d-flex justify-space-between">
              <span>یاد گرفتن vue</span>

              <v-menu class="test-menus">
                <template v-slot:activator="{ props }">
                  <v-btn min-width="40" class="pr-0 pl-0 icon-menu-item sub-menu-item" v-bind="props">
                    <v-icon size="x-large">mdi-dots-horizontal</v-icon>
                  </v-btn>
                </template>
                <v-list class="shadow list-todo-box">
                  <v-list-item v-for="(item, index) in subMenuItems" :key="index" :value="index">
                    <template v-slot:prepend>
                      <v-icon :icon="item.icon"></v-icon>
                    </template>
                    <v-list-item-title>{{ item.title }}</v-list-item-title>
                  </v-list-item>
                </v-list>
              </v-menu>

            </div>
            <div class="todo-check mt-7 d-flex justify-space-between">
              <div class="input-check d-flex align-center">
                <input type="checkbox" class="ml-2">
                <span class="task-details">قسمت 1</span>
              </div>

              <div class="icons">
                <v-btn min-width="5" max-height="18" class="pr-0 pl-0">
                  <v-icon color="green">mdi-check</v-icon>
                  <v-tooltip location="bottom" activator="parent">انجام شده</v-tooltip>
                </v-btn>
                <v-icon color="orange" class="mr-2">mdi-chevron-double-up</v-icon>
              </div>
            </div>
          </div>
          <div class="todo-list">
            <div class="title d-flex justify-space-between">
              <span>یاد گرفتن vue</span>

              <v-menu class="test-menus">
                <template v-slot:activator="{ props }">
                  <v-btn min-width="40" class="pr-0 pl-0 icon-menu-item sub-menu-item" v-bind="props">
                    <v-icon size="x-large">mdi-dots-horizontal</v-icon>
                  </v-btn>
                </template>
                <v-list class="shadow list-todo-box">
                  <v-list-item v-for="(item, index) in subMenuItems" :key="index" :value="index">
                    <template v-slot:prepend>
                      <v-icon :icon="item.icon"></v-icon>
                    </template>
                    <v-list-item-title>{{ item.title }}</v-list-item-title>
                  </v-list-item>
                </v-list>
              </v-menu>

            </div>
            <div class="todo-check mt-7 d-flex justify-space-between">
              <div class="input-check d-flex align-center">
                <input type="checkbox" class="ml-2">
                <span class="task-details">قسمت 1</span>
              </div>

              <div class="icons">
                <v-btn min-width="5" max-height="18" class="pr-0 pl-0">
                  <v-icon color="green">mdi-check</v-icon>
                  <v-tooltip location="bottom" activator="parent">انجام شده</v-tooltip>
                </v-btn>
                <v-icon color="orange" class="mr-2">mdi-chevron-double-up</v-icon>
              </div>
            </div>
          </div>
        </div>

        <v-btn class="create">
          <v-icon>mdi-plus</v-icon>
          ایجاد
        </v-btn>
      </v-col>

      <v-col lg="3" md="6" sm="12">
        <div class="todo-title d-flex justify-space-between align-center">
          <div class="title-text">
            <span>در حال پیشرفت</span>
            <span class="mr-2">2</span>
          </div>

          <v-menu class="test-menus">
            <template v-slot:activator="{ props }">
              <v-btn min-width="40" class="pr-0 pl-0 icon-menu-item" v-bind="props">
                <v-icon size="x-large">mdi-dots-horizontal</v-icon>
              </v-btn>
            </template>
            <v-list class="shadow list-todo-box">
              <v-list-item v-for="(item, index) in menuItems" :key="index" :value="index">
                <template v-slot:prepend>
                  <v-icon :icon="item.icon"></v-icon>
                </template>
                <v-list-item-title>{{ item.title }}</v-list-item-title>
              </v-list-item>
            </v-list>
          </v-menu>
        </div>

        <div class="todo-lists">
          <div class="todo-list">
            <div class="title d-flex justify-space-between">
              <span>یاد گرفتن vue</span>

              <v-menu class="test-menus">
                <template v-slot:activator="{ props }">
                  <v-btn min-width="40" class="pr-0 pl-0 icon-menu-item sub-menu-item" v-bind="props">
                    <v-icon size="x-large">mdi-dots-horizontal</v-icon>
                  </v-btn>
                </template>
                <v-list class="shadow list-todo-box">
                  <v-list-item v-for="(item, index) in subMenuItems" :key="index" :value="index">
                    <template v-slot:prepend>
                      <v-icon :icon="item.icon"></v-icon>
                    </template>
                    <v-list-item-title>{{ item.title }}</v-list-item-title>
                  </v-list-item>
                </v-list>
              </v-menu>

            </div>
            <div class="todo-check mt-7 d-flex justify-space-between">
              <div class="input-check d-flex align-center">
                <input type="checkbox" class="ml-2">
                <span class="task-details">قسمت 1</span>
              </div>

              <div class="icons">
                <v-btn min-width="5" max-height="18" class="pr-0 pl-0">
                  <v-icon color="green">mdi-check</v-icon>
                  <v-tooltip location="bottom" activator="parent">انجام شده</v-tooltip>
                </v-btn>
                <v-icon color="orange" class="mr-2">mdi-chevron-double-up</v-icon>
              </div>
            </div>
          </div>
          <div class="todo-list">
            <div class="title d-flex justify-space-between">
              <span>یاد گرفتن vue</span>

              <v-menu class="test-menus">
                <template v-slot:activator="{ props }">
                  <v-btn min-width="40" class="pr-0 pl-0 icon-menu-item sub-menu-item" v-bind="props">
                    <v-icon size="x-large">mdi-dots-horizontal</v-icon>
                  </v-btn>
                </template>
                <v-list class="shadow list-todo-box">
                  <v-list-item v-for="(item, index) in subMenuItems" :key="index" :value="index">
                    <template v-slot:prepend>
                      <v-icon :icon="item.icon"></v-icon>
                    </template>
                    <v-list-item-title>{{ item.title }}</v-list-item-title>
                  </v-list-item>
                </v-list>
              </v-menu>

            </div>
            <div class="todo-check mt-7 d-flex justify-space-between">
              <div class="input-check d-flex align-center">
                <input type="checkbox" class="ml-2">
                <span class="task-details">قسمت 1</span>
              </div>

              <div class="icons">
                <v-btn min-width="5" max-height="18" class="pr-0 pl-0">
                  <v-icon color="green">mdi-check</v-icon>
                  <v-tooltip location="bottom" activator="parent">انجام شده</v-tooltip>
                </v-btn>
                <v-icon color="orange" class="mr-2">mdi-chevron-double-up</v-icon>
              </div>
            </div>
          </div>
        </div>

        <v-btn class="create">
          <v-icon>mdi-plus</v-icon>
          ایجاد
        </v-btn>
      </v-col>

      <v-col lg="3" md="6" sm="12">
        <div class="todo-title d-flex justify-space-between align-center">
          <div class="title-text">
            <span>در حال بررسی</span>
            <span class="mr-2">0</span>
          </div>

          <v-menu class="test-menus">
            <template v-slot:activator="{ props }">
              <v-btn min-width="40" class="pr-0 pl-0 icon-menu-item" v-bind="props">
                <v-icon size="x-large">mdi-dots-horizontal</v-icon>
              </v-btn>
            </template>
            <v-list class="shadow list-todo-box">
              <v-list-item v-for="(item, index) in menuItems" :key="index" :value="index">
                <template v-slot:prepend>
                  <v-icon :icon="item.icon"></v-icon>
                </template>
                <v-list-item-title>{{ item.title }}</v-list-item-title>
              </v-list-item>
            </v-list>
          </v-menu>
        </div>

        <div class="todo-lists">
        </div>

        <v-btn class="create">
          <v-icon>mdi-plus</v-icon>
          ایجاد
        </v-btn>
      </v-col>

      <v-col lg="3" md="6" sm="12">
        <div class="todo-title d-flex justify-space-between align-center">
          <div class="title-text">
            <span>انجام شده</span>
            <span class="mr-2">1</span>
          </div>

          <v-menu class="test-menus">
            <template v-slot:activator="{ props }">
              <v-btn min-width="40" class="pr-0 pl-0 icon-menu-item" v-bind="props">
                <v-icon size="x-large">mdi-dots-horizontal</v-icon>
              </v-btn>
            </template>
            <v-list class="shadow list-todo-box">
              <v-list-item v-for="(item, index) in menuItems" :key="index" :value="index">
                <template v-slot:prepend>
                  <v-icon :icon="item.icon"></v-icon>
                </template>
                <v-list-item-title>{{ item.title }}</v-list-item-title>
              </v-list-item>
            </v-list>
          </v-menu>
        </div>

        <div class="todo-lists">
          <div class="todo-list">
            <div class="title d-flex justify-space-between">
              <span>یاد گرفتن vue</span>

              <v-menu class="test-menus">
                <template v-slot:activator="{ props }">
                  <v-btn min-width="40" class="pr-0 pl-0 icon-menu-item sub-menu-item" v-bind="props">
                    <v-icon size="x-large">mdi-dots-horizontal</v-icon>
                  </v-btn>
                </template>
                <v-list class="shadow list-todo-box">
                  <v-list-item v-for="(item, index) in subMenuItems" :key="index" :value="index">
                    <template v-slot:prepend>
                      <v-icon :icon="item.icon"></v-icon>
                    </template>
                    <v-list-item-title>{{ item.title }}</v-list-item-title>
                  </v-list-item>
                </v-list>
              </v-menu>

            </div>
            <div class="todo-check mt-7 d-flex justify-space-between">
              <div class="input-check d-flex align-center">
                <input type="checkbox" class="ml-2">
                <span class="task-details">قسمت 1</span>
              </div>

              <div class="icons">
                <v-btn min-width="5" max-height="18" class="pr-0 pl-0">
                  <v-icon color="green">mdi-check</v-icon>
                  <v-tooltip location="bottom" activator="parent">انجام شده</v-tooltip>
                </v-btn>
                <v-icon color="orange" class="mr-2">mdi-chevron-double-up</v-icon>
              </div>
            </div>
          </div>
        </div>

        <v-btn class="create">
          <v-icon>mdi-plus</v-icon>
          ایجاد
        </v-btn>
      </v-col>

    </v-row>
  </v-container>
</template>


<style lang="scss" scoped>
.admin-icon {
  width: 34px;
  height: 34px;

  span {
    left: 8px;
    font-size: 14px;
  }
}

.icon-add-user {
  background: #DFE1E6;

  i {
    color: #7b8699;
    font-size: 22px;
    top: 4px;
    right: 6px;
  }
}

.v-btn {
  &:hover {
    background: #f6f6f6;
  }

  &:focus {
    background: #eeeeee;
  }
}

.todo-lists {
  background: #f4f5f7;
  min-height: 355px;
  padding: 20px 7px 0;
  overflow: auto;

  .todo-list {
    background: #fff;
    padding: 12px;
    border-radius: 5px;
    margin-bottom: 6px;
    box-shadow: 0 1px 1px #091e4240, 0 0 1px 1px #091e4221;

    .sub-menu-item {
      visibility: hidden;
      opacity: 0;
      transition: all 0.2s ease-in-out;
    }

    &:hover .sub-menu-item {
      visibility: visible;
      opacity: 1;
    }

  }
}

.todo-title {
  background: #f4f5f7;
  border-bottom: 1px solid #dbdbdb;
  height: 48px;
  padding: 0 7px;
}

.create {
  padding: 0 12px;
  background: #f4f5f7;
  width: 100%;
  display: flex;
  justify-content: start;
  height: 38px !important;
}

.icon-menu-item {
  background: #f4f5f7;
}

.task-details {
  color: #7a869a;
  font-size: 12.5px;
}

.input-check {

  input[type="checkbox"] {
    accent-color: #349bc5;
    width: 16px;
    height: 16px;
    position: relative;
    top: -1px;
  }
}

.icons {
  .v-btn:hover {
    background: #fff;
    border: 50px;
  }

  .v-btn:hover {
    background: transparent;
  }
}
</style>