<template>
    <h2>Create an account</h2>
    <div class="form-container">
        <input v-model="text" placeholder="Name" class="form">
        <input type="tel" placeholder="Phone number" class="form">
        <button class="btn">Sign Up</button>
    </div>
    <a href="http://" target="_blank" rel="noopener noreferrer" class="email">Use email</a>
    <h3>Date of birth</h3>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam egestas diam eu leo auctor, eu auctor mauris blandit. Maecenas vel sem at ex elementum lobortis. Aenean iaculis porta nisi, eget tincidunt turpis volutpat ac. Mauris orci neque, vehicula ut purus et, lacinia lacinia eros. In ante enim, scelerisque at eros et, pharetra auctor lectus. Mauris eget tellus quam. Nullam ultrices a sem ac volutpat. Vivamus porttitor tristique eros. Integer non pe</p>
    
<div class="container">
    <div class="cont">
    <select v-model="selectedMonth" id="months" class="form">
    <option v-for="(month, index) in months" :key='index' :value="month">{{ month }}</option>
    </select>
</div>

<div class="cont">
    <select v-model="selectedDay" id="days" class="form">
    <option v-for="day in daysInMonth" :key="day" :value="day">{{ day }}</option>
    </select>
</div>
<div class="cont">
    <select v-model="selectedYear" id="year" class="form">
        <option value="" disabled selected hidden>Year</option>
        <option v-for="year in yearsRange" :key="year" :value="year">{{ year }}</option>
    </select>
</div> 

</div>
<button class="btnnn">NEXT</button>
</template>

<script setup>
import {ref} from 'vue'
const months = ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'];
const selectedMonth = ref(months[0]);
const getDaysInMonth = (year, month) => new Date(year, month + 1, 0).getDate();
const currentDate = new Date();
const currentYear = currentDate.getFullYear();
const currentMonth = currentDate.getMonth();

const daysInMonth = ref(getDaysInMonth(currentYear, currentMonth));

const selectedDay = ref(1);

//watch for changes in month and update the number of days
const updateDaysInMonth = () => {
    daysInMonth.value = getDaysInMonth(currentYear, currentMonth);
};

//watch for changes in selected months and update the number of days


    updateDaysInMonth();


//computed property to generate an array of days in the month
// const daysArray = computed(() =>{
//     const days = [];
//     for (let i = 1; i < daysInMonth.value; i++) {
//         days.push(i);
//     }
//     return days;
// });

const startYear = 1950;
const endYear = 2012;
const yearsRange = ref(Array.from({length: endYear - startYear + 1}, (_, index) =>startYear + index));

const selectedYear = ref(startYear);





</script>

<style>
.form{
   margin-bottom: auto;
    width: 210px;
    padding: 14px 14px;
    margin: 4px;
    outline: 0;
    background-color: #fff;
    border: 1px solid #031928;
    border-radius: 3px;

}

.form-container{
    display: flex;
    flex-direction: column;
    align-items: center;
}
.btn{
    font-size: 14px;
    font-weight: 600;
    padding: 10px 20px;
    color: #fff;
    background-color: #243947;
    border-radius: 20px;
    cursor: pointer;
    border: none;
    transition: 0.2s;
   
}
.btnnn{
    font-size: 15px;
    font-weight: 600;
    padding: 15px 200px;
    color: #fff;
    background-color: #243947;
    border-radius: 20px;
    cursor: pointer;
    border: none;
    transition: 0.2s;
}
.email{
    padding-top: 700px;
}
.cont{
    margin-right: 10px;
}
.container{
    display: flex;
    justify-content: center;
}
</style>