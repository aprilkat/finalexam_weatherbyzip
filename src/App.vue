<template>
      <div class="container">
        <Header />
        <Display />


      </div>
</template>

<script>
import Display from './components/Display.vue';
import Header from './components/Header.vue';

export default {
  name: 'App',
  components: {
    Display,
    Header
  }
}
</script>

<style>
 * {
  margin: 0px;
  padding: 0px;
}
</style>
