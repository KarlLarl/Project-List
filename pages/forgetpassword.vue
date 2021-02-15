<template>
  <div>
      <div class="layout">
          <div class="background">
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
            this.$router.push('/') /*ต้องนำข้อมูล (Email) ไปยัง Gmail Google*/
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
            background-image: url('../assets/Intersect.png');
            background-repeat: no-repeat;
            background-position: left -40vh;
            background-size: 100% 100%;
            display: flex;
            flex-direction: column;
            justify-content: flex-start;
            align-items: center;
        }
    }

@media screen and (min-width: 1201px) {
/*หน้าจอใหญ่*/
    .box{
        margin-top: 150px;
        border: 1px solid #ccc;
        // border: none;
        height: fit-content;
        width: 50%;
        background-color: white;
    }
}
@media screen and (max-width: 1200px) {
/*หน้าจอเล็ก*/
    .box{
        display: flex;
        justify-content: center;
        align-items: center;
        border: none;
        height: 90%;
        width: 100%;
        background-color: rgba(255, 255, 255, 0.4);
        padding: 20px;
    }
}
</style>