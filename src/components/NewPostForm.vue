<template>
    <div class="form-container">
        <h2>Ajouter un post</h2>
        <form @submit.prevent="submitForm">
            <div>
                <label for="text">text</label>
            </div>
            <textarea v-model="content" name="text" id="text" cols="80" rows="10"></textarea>
            <div>
                <label for="image">image url</label>
            </div>
            <input v-model="imageUrl" type="text">
            <p>{{imageUrl}}</p>
            <button type=submit>Enregistrer</button>
        
        </form>
    </div>
  
</template>

<script setup>
    import { ref, defineEmits } from 'vue'

    const emit = defineEmits(['submitedForm'])

    let content = ref('')
    let imageUrl = ref('')
    function submitForm(){
        console.log('submit')
        emit('submitedForm', {
            content: content.value,
            image: imageUrl.value
            })
        content.value = ''
    }


</script>



<style>

</style>