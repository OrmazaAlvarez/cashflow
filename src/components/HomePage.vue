<template>
  <LayoutPage>
    <template #header>
      <HeaderPage />
    </template>
    <template #resume>
      <ResumePage
        :total-label="'Ahorro total'"
        :label="label"
        :total-amount="1000000"
        :amount="amount"
      >
        <template #graphic> Grafico </template>
        <template #action> boton </template>
      </ResumePage>
    </template>
    <template #movements>
      <MovementsPage />
    </template>
  </LayoutPage>
</template>
<script lang="ts">
import LayoutPage from "./LayoutPage.vue";
import HeaderPage from "./HeaderPage.vue";
import ResumePage from "./Resume/IndexPage.vue";
import MovementsPage from "./Movements/IndexPage.vue";

export default {
  components: {
    LayoutPage,
    HeaderPage,
    ResumePage,
    MovementsPage,
  },
  data() {
    return {
      label: null,
      amount: null,
    };
  },
};
</script>
