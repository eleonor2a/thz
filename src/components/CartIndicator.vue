<template>
  <router-link
      class="header__cart"
      :to="{name: 'Cart'}"
      aria-label="Корзина с товарами"
  >
    <svg v-if="productLoading" xmlns:svg="http://www.w3.org/2000/svg" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.0" width="40px" height="40px" viewBox="0 0 128 128" xml:space="preserve"><g><circle cx="16" cy="64" r="16" fill="#8ade00"/><circle cx="16" cy="64" r="14.344" fill="#8ade00" transform="rotate(45 64 64)"/><circle cx="16" cy="64" r="12.531" fill="#8ade00" transform="rotate(90 64 64)"/><circle cx="16" cy="64" r="10.75" fill="#8ade00" transform="rotate(135 64 64)"/><circle cx="16" cy="64" r="10.063" fill="#8ade00" transform="rotate(180 64 64)"/><circle cx="16" cy="64" r="8.063" fill="#8ade00" transform="rotate(225 64 64)"/><circle cx="16" cy="64" r="6.438" fill="#8ade00" transform="rotate(270 64 64)"/><circle cx="16" cy="64" r="5.375" fill="#8ade00" transform="rotate(315 64 64)"/><animateTransform attributeName="transform" type="rotate" values="0 64 64;315 64 64;270 64 64;225 64 64;180 64 64;135 64 64;90 64 64;45 64 64" calcMode="discrete" dur="880ms" repeatCount="indefinite"></animateTransform></g></svg>

    <svg width="30" height="21" fill="currentColor" v-else>
      <use xlink:href="#icon-cart"></use>
    </svg>
    <span class="header__count" aria-label="Количество товаров">{{ amountTotal }}</span>
  </router-link>
</template>

<script>
import { mapGetters, mapState } from 'vuex';

export default {
  name: 'CartIndicator',
  
  computed: {
    ...mapGetters({amountTotal: 'amountProduct'}),

    ...mapState({productLoading: 'productLoading'})
  },
}
</script>

<style scoped>

</style>