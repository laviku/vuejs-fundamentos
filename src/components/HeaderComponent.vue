<template>
  <header class="flex items-center w-screen">
    <img
      @click="reload"
      class="max-w-10"
      src="@/assets/cashflow-icon.svg"
      alt="Logo"
    />
    <h1 class="text-2xl font-bold pl-16">
      <span
        class="bg-clip-text text-transparent bg-gradient-to-r from-green-500 to-sky-500"
      >
        CashFlow
      </span>
    </h1>
  </header>
</template>

<script>
export default {
  methods: {
    reload() {
      location.reload();
    },
  },
};
</script>
