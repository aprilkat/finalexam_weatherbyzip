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
    
-->

    <div class="Display">

        <!-- Examples found in vue.js docs 
        <input v-model="zip" placeholder="Zip Code" />
        <p>Message is: {{zip}}</p>

        Choose between F and C -->
        <form>
            <label for="sip">Zip Code</label><br>
            <input type="text" id="zip" name="zip" value="65674"><br>
            <input type="radio" id="Fahrenheit" name="format" value="Fahrenheit">
            <label for="Fahrenheit">Fahrenheit</label><br>
            <input type="radio" id="Celcius" name="format" value="Celcius">
            <label for="Celcius">Celcius</label><br>
        </form>

        <h1></h1>

    </div>
</template>

<script>

export default {
    name: 'Display',
    
}
        


</script>

<style scoped>
    .Display {
        background-color: lightgray;
        color: black;
        width: 100%;
    }
</style>