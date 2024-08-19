<template>
  <LayoutComponent>
    <template #header>
      <HeaderComponent />
    </template>

    <template #resume>
      <Resume :label="'Ahorro Total'" :amount="amount" :total-amount="12500">
        <template #graphic>graphic</template>
        <template #action>Action</template>
      </Resume>
    </template>

    <template #movements>
      <Movements :movements="movements" />
    </template>
  </LayoutComponent>
</template>

<script>
import LayoutComponent from "./LayoutComponent";
import HeaderComponent from "./HeaderComponent";
import Resume from "./Resume/Index.vue";
import Movements from "./Movements/Index.vue";

export default {
  components: {
    LayoutComponent,
    HeaderComponent,
    Resume,
    Movements,
  },
  data() {
    return {
      amount: null,
      movements: [
        {
          id: 1,
          title: "Lorem Ipsum 1",
          description: "Lorem Ipsum dolor sit amet",
          amount: 15,
        },
        {
          id: 2,
          title: "Lorem Ipsum 2",
          description: "Lorem Ipsum dolor sit amet",
          amount: 22,
        },
        {
          id: 3,
          title: "Lorem Ipsum 3",
          description: "Lorem Ipsum dolor sit amet",
          amount: 7,
        },
      ],
    };
  },
};
</script>
