<script setup>

import BodyMassIndexForm from './components/BodyMassIndexForm.vue'
import 'bootstrap/dist/css/bootstrap.min.css'
import 'bootstrap-icon/font/bootstrap-icons.css'

import  {ref} from 'vue'

const totalBmi= ref('')

function calculateBMI(height, weight){// function to calculate to bmi
  const bmi = weight / (height * height)
  totalBmi.value = `The BMI is ${bmi.toFixed(2)}`
}

</script>

<template>
  <div id="app-compo">
      <h1>Body Mass Index Calculator</h1>

      <BodyMassIndexForm v-on:stats-entered="calculateBMI">
      </BodyMassIndexForm>


 <p>{{totalBmi}}</p>

  </div>


</template>

<style scoped>
#app-compo{
  border: 3px solid blue;
}

</style>
