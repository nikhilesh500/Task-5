<template>
    <div class="body">
        <div class="card" :style="{background: 'linear-gradient(to bottom right, ' + cardBackground + ', #ffffff80 99%)'}">
            <div class="names">
                <h2>Name: </h2>
                <h1>{{ name }}</h1>
            </div>
            <div class="details">
                <div>
                    <h4><b>Age: </b>{{ age }}</h4>
                    <h4><b>Plays: </b>{{ plays }}</h4>
                    <h4><b>Matches Played: </b>{{ matches }}</h4>
                </div>
                <div>
                    <h4><b>Runs Scored: </b>{{ runs }}</h4>
                    <h4><b>Team: </b>{{ team }}</h4>
                    <h4><b>Position: </b>{{ position }}</h4>
                </div>
            </div>
            <button type="button" @click="$emit('deleteCard', position)">Delete</button>
        </div>
    </div>
</template>
<script setup>
import { computed } from 'vue';

    const props = defineProps({
        name: String,
        plays: String,
        age: Number,
        matches: Number,
        runs: Number,
        team: String,
        position: Number,
    });
    const cardBackground = computed(() => {
    if (props.team === 'Chennai Super Kings') {
        return 'yellow'; 
    } else if (props.team === 'Sunrisers Hyderabad') {
        return 'orange'; 
    } else if (props.team === 'Royal Challengers Bglr') {
        return 'red'; 
    }  else if (props.team === 'Mumbai Indians') {
        return '#001aff'; 
    }  else if (props.team === 'Gujarat Titans') {
        return '#01102e'; 
    } else {
        return 'lightgray'; 
    }
});
</script>
<style>
b {
    font-weight: 450;
}
.card{
    border: none;
    border-radius: 15px;
    padding: 30px;
    margin: 20px auto;
    box-shadow: 0px 0px 4px rgba(0, 0, 0, 0.411);
    color: #000000;
}
.names {
    display: flex;
    gap: 20px;
}
.names h2 {
    font-size: 20px;
    margin: 10px 0px;
}
.details {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 20px;
}
</style>