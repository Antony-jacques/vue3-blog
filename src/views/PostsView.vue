<template>
  <div class="main">
    <div class="header">
      <h2>Les derniers possts</h2>
      <p>counter: {{counter}}</p>
      <button @click="increment">increase</button>
      <NewPostForm @submitedForm="addPost" />
    </div>
  </div>
</template>

<script setup>
    import { ref } from "vue";
    import NewPostForm from '../components/NewPostForm'



    const counter = ref(0);

    function increment() {
        counter.value += 1;
    }

    function addPost(payload){
        console.log('event in parent', payload)
    }
</script>

<style>
</style>