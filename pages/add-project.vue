<template>
    <div>
        <div class="pages">
            <div class="btnselect">
                <button class="btnadd">ADD PROJECT</button>
                <nuxt-link to="/edit-project"><button class="btnedit">EDIT PROJECT</button></nuxt-link>
                <addedit></addedit>
            </div>
        </div>
    </div>
</template>

<script>
import addedit from '@/components/addedit'

export default {
    components:{
        addedit
    }
        
}
</script>

<style lang="scss" scoped>

.pages{
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;

}
.btnselect{
    button{
        padding: 10px;
        border: 2px solid #F56868;
        border-radius: 6px 6px 0px 0px;
        font-weight: bold;
        color:  #5F5F5F;
        border-bottom: none;
    }
    .btnedit{
        background-color: #F56868;
        color: white;
        
    }
    .btnadd{
        background-color: white;
    }
}

    
</style>