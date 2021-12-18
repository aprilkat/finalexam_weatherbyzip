<template>

<!-- 
    AuthorL April Bollinger
    Date: 12/16/2021
    Program: Weather By Zip (Display.vue Component)
    Purpose: Final Exam - Demonstrate understanding of what we have learned and used over the entire semester.

    Resources:
    https://v3.vuejs.org/guide/forms.html#basic-usage
    https://www.w3schools.com/js/js_validation.asp
    https://home.openweathermap.org/api_keys
    https://www.w3schools.com/html/html_form_input_types.asp
    https://openweathermap.org/current#format
    
-->

    <div class="Display" >

        <!-- Zip Code will go here -->
        <h2><input v-model="zip" type="text" id="zip" name="zip"> <br> {{zip}} </h2>
        <input v-on:click='changeFormatF' type="radio" id="F" name="format" value="imperial">
        <label for="Fahrenheit">Fahrenheit</label><br>
        <input v-on:click='changeFormatC' type="radio" id="C" name="format" value="metric">
        <label for="Celcius">Celcius</label><br>
        <button @click="changeZip()">Search</button>

        <h2> {{n}} </h2>
        <h2 >Current Temperature:  </h2>
        <!-- Still can't reach the description of the weather -->
        <h2>Current Conditions: </h2>
    
    </div>
</template>

<script>


// Variables for the axios url.
var url1 = 'http://api.openweathermap.org/data/2.5/weather?zip=';
var url2 = ',us&units=';
var url3 = '&appid=d14cf5912674ad7d02026132cefa7cb2';
var format = 'imperial';
var zip = '35004'

export {zip, format, url1, url2, url3}


// Exporting the Display Component
export default {
    name: 'Display',
    props: [],
    data() {
        return {
            zip: zip,
            format: format,

             }
       
    },

    methods: {
        changeFormatF(){
            format = 'imperial';
        },
         changeFormatC(){
            format = 'metric';
        }, 
        changeZip() {
            zip = document.getElementById('zip').value;
            
        },
    }
    }


</script>

<style scoped>
/* Styles for the Display Component */
    .Display {
        background-color: lightgray;
        color: black;
        width: 100%;
        text-align: center;
    }

   
</style>