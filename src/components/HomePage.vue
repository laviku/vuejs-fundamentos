<template>
  <LayoutComponent>
    <template #header>
      <HeaderComponent />
    </template>
  </LayoutComponent>
</template>

<script>
import LayoutComponent from "./LayoutComponent";
import HeaderComponent from "./HeaderComponent";

export default {
  components: {
    LayoutComponent,
    HeaderComponent,
  },
};
</script>
