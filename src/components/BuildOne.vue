<template>
    <div>
   <h2>Welcome {{ userName }} !</h2>
   <button v-if="!userName" @click="promptForName" class="btn">Enter your name</button>
   <!-- <input  v-model="text" placeholder="Enter your name" class="form"> -->
   <h3>Login to MySpace</h3>
   <div class="form-container">
   <input v-model="usernameInput" placeholder="Enter your username" class="form">
   <input v-model="passwordInput" placeholder="Enter your password" class="form">
   <button @click="signIn" class="btn">Sign in</button>
   <p v-if="signedIn">Sign in successful</p>
</div>
</div>
</template>

<script>
export default{
name: 'BuildOne',
data() {
    return{
        userName: '',
        usernameInput: '',
        passwordInput: '',
        signedIn: false

    };
},
methods: {
            promptForName(){
                this.userName = prompt("Please enter your name: ");
            },
            signIn(){
                if (this.usernameInput === 'admin' && this.passwordInput === 'password' ) {
                    this.signedIn = true;
                } else {
                    alert("Incorrect username or password");
                }
            }
        }
    };

</script>

<style scoped>
p {
    text-decoration: dashed;
}
.hello {
    font-size: x-large;
}
.form{
   margin-bottom: auto;
    width: 210px;
    padding: 14px 14px;
    margin: 4px;
    outline: 0;
    background-color: #fff;
    border: 1px solid #031928;
    border-radius: 3px;

}

.form-container{
    display: flex;
    flex-direction: column;
    align-items: center;
}
.btn{
    font-size: 14px;
    font-weight: 600;
    padding: 15px 25px;
    color: #fff;
    background-color: #243947;
    border-radius: 20px;
    cursor: pointer;
    border: none;
    transition: 0.2s;
}

</style>