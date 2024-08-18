<template>
  <LayoutComponent>
    <template #header>
      <HeaderComponent />
    </template>

    <template #resume>
      <Resume :label="'Ahorro Total'" :amount="amount" :total-amount="12500" />
    </template>

    <template #movements>
      <Movements />
    </template>
  </LayoutComponent>
</template>

<script>
import LayoutComponent from "./LayoutComponent";
import HeaderComponent from "./HeaderComponent";
import Resume from "./Resume/Index.vue";
import Movements from "./Resume/Movements.vue";

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
    };
  },
};
</script>
