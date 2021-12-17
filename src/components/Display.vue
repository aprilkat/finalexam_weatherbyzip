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

    <div class="Display">

        <!-- Examples found in vue.js docs 
        <input v-model="zip" placeholder="Zip Code" />
        <p>Message is: {{zip}}</p>

        Choose between F and C 
        
        <div class="alert">
            <span class="closebtn" onclick="this.parentElement.style.display='none';">&times;</span> 
            <strong>Danger!</strong> Indicates a dangerous or potentially negative action.
        </div>


        -->
        
        <form>
            <label for="zip">Zip Code</label><br>
            <input v-model="zip" type="text" id="zip" name="zip" ><br>
            <input type="radio" id="Fahrenheit" name="format" value="Fahrenheit">
            <label for="Fahrenheit">Fahrenheit</label><br>
            <input type="radio" id="Celcius" name="format" value="Celcius">
            <label for="Celcius">Celcius</label><br>
            <input type="button" value="Submit">
        </form>

        <h1></h1>

    </div>
</template>

<script>
// Exporting the Display Component
export default {
    name: 'Display',
    
}
        


</script>

<style scoped>
/* Styles for the Display Component */
    .Display {
        background-color: lightgray;
        color: black;
        width: 100%;
    }
</style>