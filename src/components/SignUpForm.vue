<template>
    <form>
        <label>Email:</label>
        <input type="email" v-model="email">

        <label>Password:</label>
        <input type="password" v-model="password">
    </form>
  <p>{{ email }}</p>
  <p>{{ password }}</p>
</template>

<script>
export default {
    data(){
        return{
            email:"hamid",
            password:"fffff"
        }
    }

}
</script>

<style>
form{
    background-color: white;
    border-radius: 10px;
    max-width: 420px;
    margin: 60px auto ;
    padding: 40px;
    text-align: left;
}

label{
    color: #aaa;
    font-weight: bold;
    display: block;
    padding: 15px 10px;
}

input{
    display: block;
    border: none;
    border-bottom: 1px solid #ddd;
    width: 100%;
    padding: 10px 6px;
    box-sizing: border-box;
    color: #555;
}
</style>