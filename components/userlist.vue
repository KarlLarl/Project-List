<template>
    <div>
        <div style="margin-top:25px;" class="card">
            <div class="image-wrapper">
                <img :src="image"> 
            </div>
            <div class="name-txt">
                
                <div class="btn-bin">
                    <img  class="icon-trash" src="@/assets/trash-alt-solid.svg" @click="Del-data">
                </div>
                <label style="text-align:center; height:50%;">{{name}}</label>
            </div>
            
         </div>
    </div>
</template>

<script>
export default {
    props:[
        'image','name'
    ],
    data(){
        return{

        }
    }

}
</script>

<style lang="scss" scoped>
.card{
        background-color: rgb(255, 255, 255);
        box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
        padding: 10px;
        display: flex;
        margin-left: 50px;
        .image-wrapper {
            width: 40px;
            border-radius: 50%;
            overflow: hidden;
            img {
                width: 100%;
         }
    }
.name-txt{
    margin-left: 30px;
    font-weight: bold;
    color: #5F5F5F;
    height: fit-content;

    .btn-bin{
        display: flex;
        justify-content: flex-end;

        .icon-trash{
        width: 12px;
        opacity : 0.5;
    }
    }

}  
} 
</style>