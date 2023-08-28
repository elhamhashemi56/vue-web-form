<template>
    <form>
        <label>Email:</label>
        <input type="email" v-model="email">

        <label>Password:</label>
        <input type="password" v-model="password">

        <label >Role:</label>
        <select v-model="role">
            <option value="developer">Web Developer</option>
            <option value="designer">Web Designer</option>
        </select>

        <div class="terms">
            <input type="checkbox" v-model="terms">
            <label >Accept Terms and Conditions</label>
        </div>

        <hr>
        <div class="terms">
            <input type="checkbox" value="elham" v-model="names">
            <label >Elham</label>
        </div>
        <div class="terms">
            <input type="checkbox"  value="sara" v-model="names">
            <label >Sara</label>
        </div>
        <div class="terms">
            <input type="checkbox"  value="ali" v-model="names">
            <label >Ali</label>
        </div>
    </form>
  <p>{{ email }}</p>
  <p>{{ password }}</p>
  <p>{{ role }}</p>
  <p>{{ terms }}</p>
  <p>{{ names }}</p>
</template>

<script>
export default {
    data(){
        return{
            email:"hamid",
            password:"fffff",
            role:"developer",
            terms:true,
            names:[]

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

input,select{
    display: block;
    border: none;
    border-bottom: 1px solid #ddd;
    width: 100%;
    padding: 10px 6px;
    box-sizing: border-box;
    color: #555;
}

.terms{
    display: flex;
    justify-content: flex-start;
}

input[type="checkbox"]{
    padding: 0;
    margin: 0;
    width: 16px;
}
</style>