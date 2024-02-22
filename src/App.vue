
<template>
  <div class="squad-container">
    <h1>SQUAD</h1>
    <div class='props-container' >
      <PropsComponent 
      v-for="(item, index) in database" 
        :name="item.name" 
        :age="item.age" 
        :plays="item.plays" 
        :matches="item.matches"
        :runs="item.runs"
        :team="item.team"
        :position="index"
        :key="index"
        v-on:deleteCard="deleteCard"
  
      />
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import PropsComponent from './components/PropsComponent.vue';

let database = ref([
  {
    jersey: 25,
    name: 'Nikhil',
    age: 22,
    plays:'All Rounder',
    matches: 113,
    runs: 2000,
    team: 'Chennai Super Kings'
  },
  {
    jersey: 7,
    name: 'Dhoni',
    age: 42,
    plays:'Batsmen(W)(C)',
    matches: 213,
    runs: 8000,
    team: 'Chennai Super Kings'
  },
  {
    jersey: 17,
    name: 'Bhuvaneswar',
    age: 22,
    plays:'Bowler',
    matches: 173,
    runs: 672,
    team: 'Sunrisers Hyderabad'
  },
  {
    jersey: 18,
    name: 'Kohli',
    age: 32,
    plays:'Batsmen',
    matches: 310,
    runs: 672,
    team: 'Royal Challengers Bglr'
  },
  {
    jersey: 45,
    name: 'Rohit',
    age: 32,
    plays:'Batsmen',
    matches: 310,
    runs: 3672,
    team: 'Mumbai Indians'
  },
  {
    jersey: 77,
    name: 'Gill',
    age: 32,
    plays:'Batsmen',
    matches: 110,
    runs: 1672,
    team: 'Gujarat Titans'
  }
]);

const deleteCard = (position) => {
  // console.log(position,'deleteThis')
  database.value.splice(position, 1);
};
  
</script>
<style scoped>
.squad-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.props-container {
  display: flex;
  flex-wrap: wrap; /* Allow items to wrap to the next row */
  justify-content: space-evenly; /* Center items horizontally */
  width: fit-content; /* Limit the width to fit content */
  column-gap: 30px; /* Adjust the gap between items */
  margin: 0 auto;
}
</style>
