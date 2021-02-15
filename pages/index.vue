<template>
  <div>
    <div class="layout">
      <div class="back">
        <div id="btn-register" class="register">
          <nuxt-link tag="button" to="/register" class="button">Register</nuxt-link>
        </div> 
        <!-- <Button 
          :link="link"
          :colorbutton="colorbutton"
        /> -->
        <div class="boxlogin">
            <FormInput 
            @returnDataInput="checkUserLogin"
            @toPageRegister="toPageRegister"/>  
        </div>

      </div>
    </div>
  </div>
</template>

<script>
// import Button from '../components/Button'    
import FormInput from '../components/FormInput'

export default {
  components:{
    // Button,
    FormInput,
  },
  data(){
    return{
      link:'Register',
      colorbutton:'#88DDDD',
    }
  },
  methods:{
    checkUserLogin(data){
      this.$router.push('/pagecard')  /*ต้องนำข้อมูลไปตรวจสอบยัง Backend*/
    },
    toPageRegister(){
      this.$router.push('register')
    }
  }
}

</script>
<style lang="scss" scoped>
.layout{
  width: 100vw;
  height: 100vh;

  .back{
    height: 100%;
    background-image: url('../assets/Intersect.png');
    background-repeat: no-repeat;
    background-position: left -40vh;
    background-size: 100% 100%;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    align-items: center;

    .register{
      width: 100%;
  
      .button{
        border: 1px solid red;
        display: block;
        // margin-top:100px;
        background-color: #88DDDD;
        border-radius: 5px;
        margin: 10px 90px 0 auto;
        padding: 10px;
      }
    }
  }

}

@media screen and (min-width: 1201px) {
/*หน้าจอใหญ่*/
    .boxlogin{
      border: 1px solid #ccc;
      // border: none;
      height: fit-content;
      width: 50%;
      background-color: white;
    }
    .back{padding: 10px;}
}
@media screen and (max-width: 1200px) {
/*หน้าจอเล็ก*/
    #btn-register{
      display: none;
    }
    .boxlogin{
      display: flex;
      justify-content: center;
      align-items: center;
      border: none;
      height: 100%;
      width: 100%;
      padding: 20px;
      background-color: rgba(255, 255, 255, 0.4);
    }
    .back{padding: 0px;}

}
</style>
