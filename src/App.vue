<template>

<!-- 
    AuthorL April Bollinger
    Date: 12/16/2021
    Program: Weather By Zip (App.vue Component)
    Purpose: Final Exam - Demonstrate understanding of what we have learned and used over the entire semester.


    Example API call provided:
      api.openweathermap.org/data/2.5/weather?zip={zip code},{country code}&appid={API key}
-->

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
import axios from 'axios';

export default {
  name: 'App',
  components: {
    Display,
    Header,
    Footer
  },

  data() {
    return {
      results: [],
      link: 'api.openweathermap.org/data/2.5/weather?zip=65674,us&appid=2e0630953f40c91e49fb1f649ae8018f'
  }},

  mounted(){
    axios.get(this.link).then(res => {console.log(res.data);}).catch(error => {console.log(error);});

  }

}
</script>

<style>
 * {
  margin: 0px;
  padding: 0px;
}
</style>
