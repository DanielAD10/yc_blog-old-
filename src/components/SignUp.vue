<template>
    <form @submit.prevent="submit">
        <h2>Create your YC Account</h2>

        <label for="">Username</label>
        <input type="text" required v-model="username">

        <label for="">Email</label>
        <input type="email" required v-model="email">

        <label for="">Password</label>
        <input type="password" required v-model="password">
        <p>{{errMsg}}</p>

        <label for="">Batch name (Eg. YC Batch-1)</label>
        <input type="text" required v-model="batch">

        <div>
            <input type="checkbox" v-model="accept">
            <label for="" id="accept">Accept all terms and conditions</label>
        </div>

        <div class="submit">
            <button>Sign Up</button>
        </div>
      
    </form>
</template>

<script>
export default {
    data() {
        return {
            username:"",
            email:"",
            password:"",
            batch:"",
            accept:false,
            errMsg:""
        }
    },
    methods: {
        submit() {
            if(this.password.length < 8) {
                this.errMsg = "Password must be at least 8 characters...";
            }
        }
    }
}
</script>

<style>
    form{
        max-width: 420px;
        background-color: white;
        margin: 30px auto;
        padding: 40px;
        text-align: left;
        border-radius: 10px;
    }
    label {
        display: inline-block;
        text-transform: capitalize;
        color: #2c3e50;
        font-weight: bold;
        letter-spacing: 0.5px;
        margin: 25px 0 15px;
    }
    input {
        display: block;
        margin: 15px 0 20px;
        padding: 10px 6px;
        box-sizing: border-box;
        border: none;
        border-bottom: 1px solid grey;
        width: 100%;
        color: gray;
    }
    input[type="checkbox"] {
        display: inline-block;
        width: 16px;
        margin: 0 10px 0 0;
        position: relative;
        top: 1px;
    }
    #accept {
        font-size: 0.9em;
        font-weight: normal;
        font-style: italic;
    }
    button {
        padding: 8px;
        background-color: royalblue;
        border: none;
        color: white;
        border-radius: 10px;
    }
    .submit {
        text-align: center;
        margin: 15px auto;
    }
    p {
        color: crimson;
        font-size: 0.8em;
    }
</style>