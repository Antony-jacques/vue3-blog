<template>
  <div class="main">
    <div class="header">
      <h2>Les derniers possts</h2>
      <ol>
          <li v-for="post in postList" :key="post">{{post.content}}</li>
      </ol>

      <NewPostForm @submitedForm="addPost" />
    </div>
  </div>
</template>

<script setup>
    import { ref } from "vue";
    import NewPostForm from '../components/NewPostForm'

    let postList = ref([])

    function addPost(payload){
        console.log('event in parent', payload)
        postList.value.push(payload)
        console.log('postList.value', postList.value)
    }
</script>

<style>
</style>