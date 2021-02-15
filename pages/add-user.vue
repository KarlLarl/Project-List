<template>
    <div class="back-g">
        <div class="page">
            <p class="txt-head">ADD LIST</p> 
            <div style="margin-top:25px" class="card-all">
                <adduser v-for="(data,index) in listdata" :key="index"
                    :image="data.image" 
                    :name="data.name"
                />
                


            </div>
        </div>
    </div>
</template>


<script>
import adduser from '@/components/add-user'

export default {
    components:{
        adduser
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
                name: 'Unknow',
                image: require('@/assets/protest.png'),
            },{
                name: 'Unknow',
                image: require('@/assets/protest.png'),
            },{
                name: 'Unknow',
                image: require('@/assets/protest.png'),
            },{
                name: 'Unknow',
                image: require('@/assets/protest.png'),
            },{
                name: 'Unknow',
                image: require('@/assets/protest.png'),
            },{
                name: 'Unknow',
                image: require('@/assets/protest.png'),
            },{
                name: 'Unknow',
                image: require('@/assets/protest.png'),
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
    }
}

.txt-head{
    color: #5F5F5F;
    font-weight: bold;
    font-size: 24px;
}
.card-all{

    height: 500px;
    overflow:auto;
}



</style>