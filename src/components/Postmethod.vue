<template>
    <!-- we use prevent keyword to prevent refresh of the data given -->
  <form @submit.prevent="Post">
    <div>
        <label for="userId">UserId</label>
    <input type="text" id="userId" >
    </div>
    <div>
        <label for="title">Title</label>
    <input type="text" id="title" >
    </div>
    <div>
        <label for="body">Body message</label>
    <input type="text" id="body" >
    </div>
    <button>PostData</button>
  </form>
</template>

<script>
import axios from 'axios';

export default {
    name:'api-post',
    data(){
        return{
            formData:{
                userId:'',
                title:'',
                body:''
            }
        }
    },
    methods:{
        Post(){
            axios.post('https://jsonplaceholder.typicode.com/posts',this.formData)
            .then((response)=>{
console.log(response)
            }).catch((error)=>{
                console.log(error)
            })
        }
    }

}
</script>

<style>

</style>