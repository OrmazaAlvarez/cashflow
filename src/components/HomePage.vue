<template>
  <LayoutPage>
    <template #header>
      <HeaderPage />
    </template>
  </LayoutPage>
</template>
<script lang="ts">
import LayoutPage from "@/components/LayoutPage.vue";
import HeaderPage from "@/components/HeaderPage.vue";

export default {
  components: {
    LayoutPage,
    HeaderPage,
  },
};
</script>
