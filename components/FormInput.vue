<template>
  <div class="forminput">

      <div v-if="path === 'register'" class="flex-form">
        <div class="row-form">
            <label class="title">GET START</label>
        </div>
        <div id="name-pc" class="row-form box-name pdTop">
            <input class="width45" type="text" placeholder="Firstname" v-model="model_data.firstname">
            <input class="width45" type="text" placeholder="Lastname" v-model="model_data.lastname">
        </div>
         <div id="mobile-Firstname" class="row-form pdTop">
            <input class="full" type="text" placeholder="Firstname" v-model="model_data.firstname">
        </div>
        <div id="mobile-Lastname" class="row-form">
            <input class="full" type="text" placeholder="Lastname" v-model="model_data.lastname">
        </div>
         <div class="row-form">
            <input class="full" type="text" placeholder="Number Phone" v-model="model_data.phone">
        </div>
         <div class="row-form">
            <input class="full" type="text" placeholder="E-mail" v-model="model_data.mail">
        </div>
         <div class="row-form">
            <input class="full" type="password" placeholder="Password" v-model="model_data.password">
        </div>
         <div class="row-form">
            <input class="full" type="password" placeholder="Confirm Password" v-model="model_data.con_password">
        </div>
        <div class="div-btn-form">
            <button type="button"  class="btn-form" @click="returnData">SUBMIT</button>
        </div>
        <div id="btn-mobile-to-login" class="div-btn-form">
            <button type="button"  class="btn-form" @click="returnLoginPage">BACK TO LOGIN</button>
        </div>
      </div>

        <div class="flex-form" v-if="path === 'index'">
        <div class="row-form">
            <label class="title">LOGIN</label>
        </div>
         <div class="input-login pdTop">
            <input class="full" type="text" placeholder="E-mail" v-model="model_data.mail" >
        </div>
         <div class="input-login">
            <input class="full" type="password" placeholder="Password" v-model="model_data.password" repuired>
        </div>
         <div class="input-login">
            <a href="/forgetpassword" class="forgetPWD">*Forget Password</a>
        </div>
        <div class="div-btn-form">
             <button type="button" class="btn-form" @click="returnData">LOGIN</button>
        </div>
        <div id="btn-mobile-to-register" class="div-btn-form">
             <button type="button" class="btn-form" @click="returnRegisterPage">REGISTER</button>
        </div>
      </div>

     <div class="flex-form" v-if="path === 'forgetpassword'">
        <div class="row-form">
            <label class="title-forget">FORGET PASSWORD</label>
        </div>
         <div class="input-login pdTop">
            <input class="full" type="text" placeholder="E-mail" v-model="model_data.mail">
        </div>
        <div class="div-btn-form">
            <button type="button" class="btn-form" @click="returnData">SUBMIT</button>
        </div>
        <div id="btn-mobile-to-login" class="div-btn-form">
            <button type="button"  class="btn-form" @click="returnLoginPage">BACK TO LOGIN</button>
        </div>
      </div>

  </div>
</template>

<script>

export default {

    data(){
        return{
            path: '',

            model_data: {
                firstname: '',
                lastname: '',
                phone: '',
                mail: '',
                password: '',
                con_password: ''
            }
        }
    },

    methods:{
        returnData(){
            return this.$emit('returnDataInput',this.model_data)
        },
        returnRegisterPage(){
            return this.$emit('toPageRegister',true)
        },
        returnLoginPage(){
            return this.$emit('toPageLogin',true)
        }
    },
    mounted(){
        this.path = this.$route.name
    }

}

</script>

<style>
.full{width: 100%;}

.width45{width: 45%;}

.title, .title-forget{
    font-weight: 600;
    color: #5f5f5f;
}

.forminput{width: 100%;}

input{
    height: 44px;
    border-radius: 5px;
    border: 1px solid #c3c3c3;
    padding: 0px 15px;
    color: #5f5f5f;
    font-weight: 500;
    font-size: 16px;
}

input::placeholder{color: #5f5f5f;}

    .btn-form{
        padding: 12px 40px;
        background-color: #f56868; 
        height: 45px;
        color: #fff;
        font-weight: 500;
        font-size: 18px;
        border-radius: 2.5px;
        border: none;
        height: auto;
        box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.25)
    }

.row-form{padding-bottom: 20px;}

.box-name{
    display: flex;
    justify-content: space-between;
    padding-top: 30px;
}

.forgetPWD{
    font-size: 14px;
    color: #f56868;
    text-decoration: underline;
    border: none;
    background: transparent;
}

.div-btn-form{
    display: flex;
    justify-content: flex-end;
}

@media screen and (min-width: 1201px) {
/*หน้าจอใหญ่*/
    #btn-mobile-to-register,#btn-mobile-to-login{display: none;}
    .title{font-size: 60px;}
    .title-forget{font-size: 50px;}
    #mobile-Firstname, #mobile-Lastname{display: none;}

    .forminput{
        border-radius: 5px;
        border: 1px solid #c3c3c3;
        height: 100%;
        padding: 5% 10% 8% 10%;
        background-color: #fff;
    }

    .btn-form{
        width: fit-content;
        border-radius: 5px;
    }

    .pdTop{padding-top: 40px;}
    .input-login{padding-bottom: 40px;}
    .div-btn-form{padding-top: 40px;}
}

@media screen and (max-width: 1200px) {
/*หน้าจอเล็ก*/
    .title{font-size: 40px;}
    .title-forget{font-size: 35px;}
    #name-pc{display: none;}
    .row-form{text-align: center;}
    .forminput{height: fit-content;}

    .btn-form{
        width: 100%;
        border-radius: 2.5px;
    }

    .pdTop{padding-top: 20px;}
    .input-login{padding-bottom: 20px;}
    .div-btn-form{padding-top: 10px;}
}

</style>
