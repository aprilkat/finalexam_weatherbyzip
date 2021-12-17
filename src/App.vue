<template>
      <div class="container">
        <Header />
        <Display />
        <Footer />


      </div>
</template>

<script>
import Display from './components/Display.vue';
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    Display,
    Header,
    Footer
  }
}
</script>

<style>
 * {
  margin: 0px;
  padding: 0px;
}
</style>
