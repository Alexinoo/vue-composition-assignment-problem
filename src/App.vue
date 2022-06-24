<template>
  <h2>My Course Goal</h2>
  <!-- Task 1: Output your main course goal with help of the composition API -->
  <!-- Don't hardcode it into the template, instead hardcode it into the JS code -->
  <h3 v-if="myGoals.visibility">{{ myGoals.courseGoal }}</h3>
  <!-- Task 2: Toggle (show/ hide) the goal with help of the button  -->
  <button @click="toggleGoal">{{ myGoals.visibility ? 'Hide' : 'Show'}} Goal</button>
  <!-- Task 3: Manage data in three ways -->
  <!-- => Separate refs -->
  <!-- => Ref Object -->
  <!-- => Reactive Object -->
  <!-- Task 4: Also solve the assignment with the Options API -->
</template>

<script>
import { ref  } from 'vue';
export default {

  setup(){

    // const courseGoal = ref('Learn Vue and build amazing projects')
    // const visibility = ref(true)

    const myGoals = ref({
      courseGoal: 'Learn Vue and build amazing projects' ,
      visibility : true
    })

    function toggleGoal() {
      myGoals.value.visibility = !myGoals.value.visibility
    }

    return { 
      courseGoal: myGoals.value.courseGoal, 
      visibility: myGoals.value.visibility , 
      myGoals ,
      toggleGoal
       }
  }


};
</script>

<style>
html {
  font-family: sans-serif;
}
body {
  margin: 3rem;
  text-align: center;
}
</style>
