<template>
    <div class="form-container">
        <h2>Ajouter un post</h2>
        <form @submit.prevent="submitForm">
            <div>
                <label for="text">text</label>
            </div>
            <textarea v-model="content" name="text" id="text" cols="80" rows="10"></textarea>
            <p>{{content}}</p>
            <button type=submit>Enregistrer</button>
        
        </form>
    </div>
  
</template>

<script setup>
    import { ref, defineEmits } from 'vue'

    const emit = defineEmits(['submitedForm'])

    let content = ref('')
    function submitForm(){
        console.log('submit')
        emit('submitedForm', content.value)
    }


</script>



<style>

</style>