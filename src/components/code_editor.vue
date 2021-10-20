<template>  

<div class="container">
        <form action="" @submit.prevent="postData()" method="post">
            <div class="select">
                 <select name="language" v-model="post.select_language" id="language"> 
                    <option value="c">C</option>
                    <option value="c++">C++</option>
                    <option value="java">Java</option>
                    <option value="python">Python</option>
                </select>
            </div>
            
 
            <div class="codewrite">
                <textarea name="codearea" v-model="post.codearea" id="codeinput" cols="120" rows="20"></textarea>

            </div>
            <div>
                <button type="submit">run</button>
            </div>
            
        </form>
       
</div>

</template>

<script src="src/ace.js" type="text/javascript" charset="utf-8"></script> 

<script>

import axios from 'axios';
    export default{
        name:'CodeCompiler',
        data(){
            return{
                post:{
                    select_language:String,
                    codearea:null,
                }
                
            }
        },
        methods:{
            postData(){
                console.log("data ",this.post);
                axios.post(`http://localhost:3000/`,this.post).
                then(res => console.log(res.data)
                )

            }
        },
        mounted(){
            let editor = ace.edit("codeinput")
        }
    }
</script>

<style scoped>
    .container{
        width:80%;
        margin: 0 auto;
        text-align: left;
    }
    .codewrite{
        position:relative;
    }
</style>