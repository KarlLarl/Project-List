<template>
  <div>
      <div class="layout">
          <div class="background">
            <div id="btn-link-login" class="tologin">
                <nuxt-link tag="button" to="/" class="button">Login</nuxt-link>
            </div> 
              <div class="box">
                  <FormInput  
                  @returnDataInput="linkcard"
                  @toPageLogin="toPageLogin"/>
              </div>
          </div>
      </div>
  </div>
</template>

<script>

import FormInput from '../components/FormInput'

export default {
    components:{
        FormInput,
    },
    methods:{
        linkcard(data){
            this.$router.push('/pagecard') /*ต้องตรวจสอบข้อมูลในฝั่ง Backend แล้ว บันทึกข้อมูลก่อน*/
        },
        toPageLogin(){
            this.$router.push('/')
        }
    }
}

</script>

<style lang="scss" scoped>
    .layout{
        width: 100vw;
        height: 100vh;
        .background{
            height: 100%;
            background-image: url('../assets/bule.png');
            background-repeat: no-repeat;
            background-position: right 50vh;
            background-size: 100% 100%;
            display: flex;
            flex-direction: column;
            justify-content: flex-start;
            align-items: center;

            .tologin{
                width: 100%;

                .button{
                    border: 1px solid red;
                    display: block;
                    // margin-top:100px;
                    background-color: white;
                    border-radius: 5px;
                    margin: 10px 90px 0 auto;
                    padding: 10px;
                }
            }
        }
    }

@media screen and (min-width: 1201px) {
/*หน้าจอใหญ่*/

    .box{
        border: 1px solid #ccc;
        height: fit-content;
        width: 60%;
        background-color: white;
    }

}
@media screen and (max-width: 1200px) {
/*หน้าจอเล็ก*/
    #btn-link-login{
        display: none;
    }
    .box{
        display: flex;
        justify-content: center;
        align-items: center;
        border: none;
        height: 100%;
        width: 100%;
        background-color: rgba(255, 255, 255, 0.4);
        padding: 20px;
    }
}
</style>