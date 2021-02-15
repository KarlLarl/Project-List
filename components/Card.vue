<template>
    <div class="mycard">
        <div class="title" v-bind:style="{ 'background-image': 'url(' + img + ')' }">
            <div class="icon-edit">
                <i class="material-icons i-edit">edit</i>
            </div>
            <div class="text-title">
                {{title}}
            </div>
        </div>
        <div class="usercreate">
            <img class="user-img" :src="imgUser">
            <div class="text-label">
                <label class="name-user">{{nameUser}}</label><br>
                <label class="status-user">{{status}}</label>
            </div>
        </div>
    </div>
</template>

<script>

export default {

    props:['title','img','imgUser','nameUser','status'],

    methods:{
        selectImg(){
            console.log('click')
        }
    }

}
</script>

<style scoped>

@media screen and (min-width: 501px) {
/*หน้าจอใหญ่*/
   .mycard{
        width: 250px;
        height: 220px;
    }
}
@media screen and (max-width: 500px) {
/*หน้าจอเล็ก*/
    .mycard{
        width: 100%;
        max-width: 500px;
        height: 30vh;
    }
}

.mycard{
    border-radius: 10px;
    box-shadow: 0px 5px 5px 0px rgba(224,224,224,0.5);
}

.title{
    width: 100%;
    height: 75%;
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
    padding: 10px;
    background-repeat: no-repeat;
    background-position: center;
    background-size: 100% 100%;
    box-shadow: inset 0px 200px 190px -200px rgba(0,0,0,1);
}
.title:hover{
    box-shadow: none;
}
.usercreate{
    width: 100%;
    height: 25%;
    background-color: #fff;
    border-bottom-left-radius: 10px;
    border-bottom-right-radius: 10px;
    padding: 0px 10px;
}
.icon-edit{
    height: fit-content;
    width: 100%;
    position: relative;
}
.i-edit{
    position: absolute;
    right: 0px;
    color: #fff;
    font-size: 20px;
}
.text-title{
    margin-top: 30px;
    color: #fff;
    font-size: 22px;
    font-weight: 600;
}
.user-img{
    width: 30px;
    height: 30px;
    border-radius: 50%;
    position: relative;
    top: 50%;
    left: 7%;
    transform: translate(-50%, -50%);
    margin-right: 10px;
    float: left;
}
.text-label{
    line-height: 1;
    position: relative;
    top: 45%;
    transform: translate(0%, -50%);

}
.name-user,.status-user{
    margin: 0px;
}
.name-user{
    font-weight: 400;
    font-size: 12px;
}
.status-user{
    font-weight: 200;
    font-size: 10px;
}

</style>