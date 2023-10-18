  <script>
  export default {
  
  }
  </script>

<template>
  <div>
    <v-layout>
      <v-navigation-drawer permanent class="slide-bar">
        <div class="navigation d-flex ">
          <v-list nav>
            <v-list-item>اصلی</v-list-item>
            <v-list-item
              prepend-icon="mdi-home-outline"
              title="خانه"
              value="inbox"
            ></v-list-item>
            <v-list-item
              prepend-icon="mdi-inbox"
              title="صندوق ورودی"
              value="supervisors"
            ></v-list-item>
            <v-list-item
              prepend-icon="mdi-chart-bell-curve-cumulative"
              title="تجزیه و تحلیل"
              value="clockin"
            ></v-list-item>
  
            <v-list-item class="mt-2">برنامه ریزی</v-list-item>
            <v-list-item
              prepend-icon="mdi-calendar-clock"
              title="جدول زمانی"
              value="time"
            ></v-list-item>
            <v-list-item
              prepend-icon="mdi-human-male-board-poll"
              title="هیئت مدیره"
              value="board"
            ></v-list-item>
            <v-list-item
              prepend-icon="mdi-finance"
              title="گزارش‌ها"
              value="reports"
            ></v-list-item>
            <v-list-item
              prepend-icon="mdi-newspaper-variant-multiple-outline"
              title="مسائل"
              value="issue"
            ></v-list-item>
            
            <v-list-item class="mt-2">توسعه دهنده</v-list-item>
            <v-list-item
              prepend-icon="mdi-xml"
              title="کد"
              value="code"
            ></v-list-item>
            <v-list-item
              prepend-icon="mdi-desktop-classic"
              title="منتشر شده"
              value="release"
            ></v-list-item>
          </v-list>

          <div class="feedbacks">
            <p>شما در یک پروژه تیمی هستید</p>
            <p class="mt-2 feedback">
              بازخورد بدهید
              <v-icon>mdi-bullhorn-outline</v-icon>
            </p>
          </div>
        </div>
      </v-navigation-drawer>
    </v-layout>
  </div>
</template>


<style lang="scss" scoped>
.navigation {
  height: 93vh;
  flex-direction: column;
  justify-content: space-between;

  .feedbacks {
    margin-bottom: 15px;
    text-align: center;
    font-size: 12px;
    font-family: Vazir-light;  
    color: #344563;

    .feedback {
      font-size: 12px;
      font-family: Vazir-medium;
      color: #44546f;

      i {
        font-size: 16px;
      }
    }
  }
}

</style>