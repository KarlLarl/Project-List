<template>
    <div class="respon">
        <div class="card">
            <div class="image-wrapper">
                <img :src="image"> 
            </div>
            <div class="name-txt">
                <label style="text-align:center;">{{name}}</label>
                <div>
                    <label class="btn-add">ADD</label>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props:[
        'image','name'
    ]
    
}
</script>

<style lang="scss" scoped>


.card{
        background-color: rgb(255, 255, 255);
        box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
        padding: 10px;
        display: flex;
        width: 500px;
        
        .image-wrapper {
            width: 40px;
            border-radius: 50%;
            overflow: hidden;
            img {
                width: 100%;

        .flex-add{
            display: flex;

        }
         }
    }
.name-txt{
    margin-left: 30px;
    font-weight: bold;
    color: #5F5F5F;
    .btn-add{
        color: red;
        margin-left: 310px;
        text-decoration-line: underline; 
    }   
    }

}
</style>