<template>
    <div>
        <div v-if="checkDetailBtn(textBtn) === 0">
            <button class="btnIcon" type="button" onclick="window.location.href='/pagecard'">
                <img src="https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/icon%2Fblack.png?alt=media&token=eaf18282-0778-4edf-9b31-acc7ac529db6">
            </button>
        </div>
        <div v-else>
            <button class="btn-nav" type="button" @click="clickBTN(textBtn)">{{textBtn}}</button>
        </div>
    </div>
</template>
<script>

export default {
    props:['textBtn'],
    data(){
        return {
            classIcon: ''
        }
    },
    methods: {
       checkDetailBtn(text){
            let array = text.split('=>')
            if(array.length === 2){
                this.classIcon = `${array[1]}`
                console.log(array[1])
                return 0;
            }else{
                return 1;
            }
       },
       clickBTN(text){
           if(text === 'Add Project'){
               console.log('Add Project')
           }else{
               console.log('Log Out')
           }
       }
    }
}
</script>
<style scoped>
@import url('https://fonts.googleapis.com/css?family=Prompt:100,200,400,500,600,700&display=swap');
.btn-nav{
    background-color: #f2d7c3;
    border: none;
    border-radius: 5px;
    padding: 10px;
    font-weight: 600;
    height: 40px;
    width: fit-content;
}
.btnIcon{
    background-color: #f2d7c3;
    border: none;
    border-radius: 5px;
    padding: 10px;
    font-weight: 600;
    height: 40px;
    width: 40px;
}
.btn-nav img{
    width: 100%;
    height: 100%;
}

</style>