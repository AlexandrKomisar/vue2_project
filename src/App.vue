<template>
  <div id="app">
    <app-header/>
    <app-tabs/>
    <app-exchange/>
    <app-footer/>
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import AppTabs from './components/AppTabs.vue';
import AppExchange from './components/AppExchange.vue';
import AppFooter from './components/AppFooter.vue';

export default {
  name: 'App',
  components: {
    AppHeader,
    AppTabs,
    AppExchange,
    AppFooter,
  },
};
</script>

<style>
*{
  box-sizing: border-box;
  margin: 0;
}
</style>
