<template>
  <div>
    <h5 v-if="errorMsg">{{errorMsg}}</h5>
    <button @click="getmethod">Load posts</button>
  <div v-for="post in posts" :key="post.id">
<h4> {{post.id}}. {{post.title}}</h4>  
    <p>{{post.body}}</p>
    <hr/>
</div>
  </div>
</template>

<script>


import axios from 'axios'

export default {
name:'api-get',
data(){
    return{
        posts:[],
        errorMsg:''
    }
},
methods:{
    getmethod(){
        axios
        .get('https://jsonplaceholder.typicode.com/posts')
        .then((response)=>{
            this.posts=response.data
        }).catch((error)=>{
            this.errorMsg=error
        })
    }
}
}
</script>

<style>

</style>