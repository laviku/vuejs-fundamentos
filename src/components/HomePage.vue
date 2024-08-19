<template>
  <LayoutComponent>
    <template #header>
      <HeaderComponent />
    </template>

    <template #resume>
      <Resume :label="'Ahorro Total'" :amount="amount" :total-amount="12500">
        <template #graphic><Graphic :amounts="amounts" /></template>
        <template #action><Action @create="create" /></template>
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
import Action from "./Action.vue";
import Graphic from "./Resume/Graphic.vue";

export default {
  components: {
    LayoutComponent,
    HeaderComponent,
    Resume,
    Movements,
    Action,
    Graphic,
  },
  data() {
    return {
      amount: null,
      movements: [
        {
          id: 1,
          title: "Lorem Ipsum 1",
          description: "Lorem Ipsum dolor sit amet",
          amount: 150,
          time: new Date("07-18-2024"),
        },
        {
          id: 2,
          title: "Lorem Ipsum 2",
          description: "Lorem Ipsum dolor sit amet",
          amount: 600,
          time: new Date("08-15-2024"),
        },
        {
          id: 3,
          title: "Lorem Ipsum 3",
          description: "Lorem Ipsum dolor sit amet",
          amount: -400,
          time: new Date("08-16-2024"),
        },
        {
          id: 4,
          title: "Lorem Ipsum 4",
          description: "Lorem Ipsum dolor sit amet",
          amount: 100,
          time: new Date("08-17-2024"),
        },
      ],
    };
  },
  computed: {
    amounts() {
      const lastDaysAmounts = this.movements
        .filter((m) => {
          const today = new Date();
          const oldDate = today.setDate(today.getDate() - 30);

          return m.time >= oldDate;
        })
        .map((m) => m.amount);

      return lastDaysAmounts.map((m, i) => {
        const lastMovements = lastDaysAmounts.slice(0, i);

        return lastMovements.reduce((suma, movement) => {
          return suma + movement;
        }, 0);
      });
    },
  },
  methods: {
    create(movement) {
      this.movements.push(movement);
    },
  },
};
</script>
