<template>
    <div class="back-g">
        <div class="page">
            <p class="txt-head">USER LIST</p> 
            <div class="card-all">
                <userlist v-for="(data,index) in listdata" :key="index"
                    :image="data.image" 
                    :name="data.name"
                />
                <div class="adduser">
                    <button></button>
                    </div>
                


            </div>
        </div>
    </div>
</template>


<script>
import userlist from '@/components/userlist'

export default {
    components:{
        userlist
    },
    data(){
        return{
            listdata:[{
               name: 'Melon',
               image: require('@/assets/image01.png'),
            },
            {
                name: 'Candy',
                image: require('@/assets/image02.jpg'),
            },{
                name: 'Apple',
                image: require('@/assets/image03.jpg'),
            },{
                name: 'Crow',
                image: require('@/assets/image04.jpg'),
            },{
                name: 'Crow',
                image: require('@/assets/image04.jpg'),
            },
            {
                name: 'Candy',
                image: require('@/assets/image02.jpg'),
            },{
                name: 'Apple',
                image: require('@/assets/image03.jpg'),
            },{
                name: 'Crow',
                image: require('@/assets/image04.jpg'),
            },{
                name: 'Crow',
                image: require('@/assets/image04.jpg'),
            }
            ]
        }
    }
    
}
</script>

<style lang="scss" scoped>
.back-g{
    padding: 25px;
    display: flex;
    justify-content: center;
    align-items: center;
    .page{
        background-color: white;
        box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
        width: fit-content;
        height: fit-content;
        padding: 25px;
        border-radius: 4px;
        .adduser{
            background-color: rgb(255, 255, 255);
            box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
            padding:  19px 50px;
            margin-top: 25px;
            margin-left: 50px;
            button{
                border-radius: 50px;
                width: 25px;
                height: 25px;
                border: 1px solid black;
                background-color: white;
                background-image: url('../assets/add.svg');
                background-size: 15px;
                background-repeat: no-repeat;
                background-position: 50%
                
            }
        }
    }
}
.card-all{
    display: flex;
    flex-wrap: wrap;
}
.txt-head{
    color: #5F5F5F;
    font-weight: bold;
    font-size: 24px;
}
</style>