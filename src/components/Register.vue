<script setup>
import { ref } from 'vue';
import { reactive } from 'vue';

const email = ref('');
const usuarios = reactive([])

function register(data){
    if(data){
        usuarios.push(data.value);
    }
}

function onSubmit(){
    register(email);
    console.log(usuarios[0]);
}
</script>
<template>
    <form @submit.prevent="onSubmit">
      <input type="text" placeholder="digite seu e-mail" v-model="email">
      <button type="submit">Cadastrar</button>
    </form>
    <ul>
      <li v-for="(usuario, index) in usuarios" :key="index">{{ usuario }}</li>
    </ul>
</template>