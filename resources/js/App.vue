<template>
    <div class="container">
        <h1>Home Vue</h1>
        <h2>I miei post:</h2>

        <ul>
            <li v-for="post in posts" :key="post.id">
                <h3>{{post.title}}</h3>
                <p>{{post.content}}</p>
            </li>
        </ul>
    </div>
</template>

<script>

// import Axios from 'axios';

export default {
    name:'App',
    data(){
        return{
            apiUrl:'http://127.0.0.1:8000/api/posts',
            posts: null
        }
    },
    methods:{
        getApi(){
            // console.log('API');
            // console.log(axios);

            axios.get(this.apiUrl)
            .then(res => {
                this.posts = res.data;
                console.log(this.posts);
            })

        }

    },
    mounted(){
        this.getApi();
    }


}
</script>

<style>

</style>
