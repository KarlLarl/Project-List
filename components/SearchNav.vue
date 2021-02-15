<template>
    <div>
        <label class="text-show">
            <label class="text-title">{{textSearch}}</label>
        </label>
        <div class="group-search">
            <div class="myicon">
                <img :src="icon_url">
            </div>
            <input class="search-input" type="text" 
            :placeholder="textPlaceholder" 
            v-model="dataSearch" 
            @keyup="returnData">
        </div>
    </div>
</template>
<script>

export default {
    props:['textSearch','textPlaceholder'],
    data(){
        return {
            dataSearch: '',
            icon_url: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/icon%2Fsearch.png?alt=media&token=133abfae-18dc-418a-9c9e-63aa8ed7a874'
        }
    },
    methods: {
       returnData(){
           this.$emit('setSearch',this.dataSearch)
       }
    }
}
</script>
<style scoped>
.text-show{
    margin-left: 10px;
    float: left;
    height: 40px;
    position: relative;
}
.group-search{
    float: left;
    margin-left: 10px;
    height: 40px;
}
.text-title{
    position: absolute;
    top: 50%;
    transform: translate(-100%, -55%);
}
.myicon{
    padding: 8px;
    background-color: #e0e0e0;
    width: 40px;
    float: left;
    height: 100%;
    border-top-left-radius: 5px;
    border-bottom-left-radius: 5px;
    text-align: center;
}
.myicon img{
    width: 100%;
    height: 100%;
}
.search-input{
    background-color: #e0e0e0;
    border: none;
    padding: 8px 8px 8px 0px;
    border-top-right-radius: 5px;
    border-bottom-right-radius: 5px;
    height: 100%;
}
.search-input:focus{
    outline-width: 0;
}
</style>