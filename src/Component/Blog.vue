<template>
    <div>
    <h1>Blog Article</h1>
    <div v-for="(blog,id) in blogs" :key="id">
    <h2>{{blog.title}}</h2>
    <p>{{blog.body}}</p>

       </div>
    </div>
</template>
<script>
export default {
    data(){
        return{
            blogs:[]

      }
    },
    created(){
        this.$http.get('https://jsonplaceholder.typicode.com/posts').then((data)=>{
           
            this.blogs=data.body.slice(0,10)
        })
    }
  }
</script>
<style>

</style>