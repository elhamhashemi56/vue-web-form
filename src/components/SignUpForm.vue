<template>
    <form @submit.prevent="handleSubmit">
        <label>Email:</label>
        <input type="email" v-model="email">

        <label>Password:</label>
        <input type="password" v-model="password">
        <p class="error">{{ passwordError }}</p>

        <label >Role:</label>
        <select v-model="role">
            <option value="developer">Web Developer</option>
            <option value="designer">Web Designer</option>
        </select>

        <div>
            <label>Skills: <p>(Please press (Alt + ,) for tag to adding)</p></label>
            <input type="text" @keyup.alt="addSkill" v-model="tempSkill">
            <div v-for="item in skills" :key="item" class="pill">
               <div @click="handleDelete(item)">{{ item }}</div> 
            </div>
        </div>

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

        <div class="submit">
            <button>Create an Account</button>
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
            email:"",
            password:"",
            role:"developer",
            terms:true,
            names:[],
            tempSkill:"",
            skills:[],
            passwordError:""

        }

    },
    methods:{
        addSkill(e){
            console.log(e);
            if(e.key === ","){
                if(!this.skills.includes(this.tempSkill)){
                    this.skills.push(this.tempSkill)
                }
                this.tempSkill=""
            }
        },
        handleDelete(item){
            console.log(item);
            const skills=this.skills.filter(ele=>{
                return ele !== item
            })

            this.skills=skills
        },
        handleSubmit(){
            console.log("handle submit");
            this.passwordError=this.password.length >5 ? "" : "Password is not more than 5 Char"
            if(!this.passwordError){
                console.log("Form submited");
            }
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
.pill{
    display: inline-block;
    padding: 10px;
    margin: 10px;
    background-color: #eee;
    border-radius:50%;
    cursor: pointer;
}

button{
    border: 0;
    padding: 10px 20px;
    background-color: #0b6dff;
    border-radius: 20px;
    color: white;
}

.submit{
   text-align: center;
}
.error{
    color: red;
}
</style>