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

    <v-row justify="space-between mt-3">
      <v-col>
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
      <v-col align="left">
        <div class="icon-action">
          <v-btn>
            <v-icon class="ml-1">mdi-share-variant-outline</v-icon>
            اشتراک گذاری
          </v-btn>

          <v-btn>
            <v-icon class="ml-1">mdi-filter-variant</v-icon>
            فیلتر
          </v-btn>

          <v-btn>
            <v-icon class="ml-1">mdi-dots-horizontal</v-icon>
            بیشتر
          </v-btn>
        </div>
      </v-col>
    </v-row>


    <!-- <div class="todo-lists ">
      <div class="aa d-flex mt-4">
        <div class="todo-list">1</div>
        <div class="todo-list">2</div>
        <div class="todo-list">3</div>

        <div class="todo-list">

        </div>

      </div>
    </div> -->

    <v-row>
      <v-col cols="3">
        <div class="todo-title d-flex justify-space-between align-center">
          <div class="title-text">
            <span>انجام کار</span>
            <span class="mr-2">3</span>
          </div>
          <v-icon>mdi-dots-horizontal</v-icon>
        </div>
        
        <div class="todo-lists">
          <div class="todo-list">
            <div class="title d-flex justify-space-between">
              <span>یاد گرفتن vue</span>
              <v-icon>mdi-dots-horizontal</v-icon>
            </div>
            <div class="todo-check mt-5 d-flex justify-space-between">
              <div class="input-check d-flex">
                <input type="checkbox" class="ml-2">
                <span>قسمت 1</span>
              </div>

              <div class="icons">
                <v-icon size="small" color="green">mdi-check</v-icon>
                <v-icon size="small" color="orange" class="mr-2">mdi-chevron-double-up</v-icon>
              </div>
            </div>
          </div>
          <div class="todo-list">
            <div class="title d-flex justify-space-between">
              <span>یاد گرفتن vue</span>
              <v-icon>mdi-dots-horizontal</v-icon>
            </div>
            <div class="todo-check mt-5 d-flex justify-space-between">
              <div class="input-check d-flex">
                <input type="checkbox" class="ml-2">
                <span>قسمت 1</span>
              </div>

              <div class="icons">
                <v-icon size="small" color="green">mdi-check</v-icon>
                <v-icon size="small" color="orange" class="mr-2">mdi-chevron-double-up</v-icon>
              </div>
            </div>
          </div>
          <div class="todo-list">
            <div class="title d-flex justify-space-between">
              <span>یاد گرفتن vue</span>
              <v-icon>mdi-dots-horizontal</v-icon>
            </div>
            <div class="todo-check mt-5 d-flex justify-space-between">
              <div class="input-check d-flex">
                <input type="checkbox" class="ml-2">
                <span>قسمت 1</span>
              </div>

              <div class="icons">
                <v-icon size="small" color="green">mdi-check</v-icon>
                <v-icon size="small" color="orange" class="mr-2">mdi-chevron-double-up</v-icon>
              </div>
            </div>
          </div>
        </div>

        <div class="create">
          <v-icon >mdi-plus</v-icon>
          ایجاد
        </div>



      </v-col>
      <v-col cols="3">2</v-col>
      <v-col cols="3">3</v-col>
      <v-col cols="3">4</v-col>
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
  max-height: 500px;
  padding: 20px 7px 0;
  overflow: auto;

  .todo-list {
    background: #fff;
    padding: 12px;
    border-radius: 5px;
    margin-bottom: 4px;
    box-shadow: 0 1px 1px #091e4240,0 0 1px 1px #091e4221;
    // margin-left: 15px;
    // padding: 10px 15px;
    // border-radius: 5px;
    // width: 270px;

  }
}
.todo-title {
  background: #f4f5f7;
  border-bottom: 1px solid #dbdbdb;
  height: 48px;
  padding: 0 7px;
}

.create {
  padding: 10px 7px;
  background: #f4f5f7;
}
</style>