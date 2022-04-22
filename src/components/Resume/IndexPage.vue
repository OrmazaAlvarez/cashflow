<template>
  <main>
    <p>{{ showLabel }}</p>
    <h1>{{ showCurrency }}</h1>
    <div class="graphic">
      <slot name="graphic"></slot>
    </div>
    <div class="action">
      <slot name="action"></slot>
    </div>
  </main>
</template>
<script lang="ts">
const currencyFormatter = new Intl.NumberFormat("es-EC", {
  style: "currency",
  currency: "USD",
});
export default {
  props: {
    totalLabel: {
      type: String,
    },
    label: {
      type: String,
      default: null,
    },
    totalAmount: {
      type: Number,
    },
    amount: {
      type: Number,
      default: null,
    },
  },
  computed: {
    showLabel() {
      return this.label !== null ? this.label : this.totalLabel;
    },
    showAmount() {
      return this.amount !== null ? this.amount : this.totalAmount;
    },
    showCurrency() {
      return currencyFormatter.format(this.showAmount);
    },
  },
};
</script>
<style scoped>
main {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: 100%;
}
h1,
p {
  margin: 0;
  text-align: center;
}
h1 {
  margin-top: 14px;
  color: var(--brand-green);
}
.graphic {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  padding: 48px 24px;
  box-sizing: border-box;
}
</style>
