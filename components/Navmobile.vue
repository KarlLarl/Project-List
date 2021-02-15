<template>
    <div>
    <div class="box-nav">
        <div class="path-title">
            <label class="text-path-title">{{path}}</label>
        </div>
        <div class="nav-detail">
            <div class="head-title">
                <label class="text-head-title">{{head}}</label>
            </div>
            <div class="menu">
                <button class="btn-menu" type="button" @click="showListMenu">
                    <i class="material-icons">menu</i>
                </button>
            </div>
        </div>
    </div>
        <div class="nav-list-menu" v-if="statusShowMenu === true">
            <ul class="list-menu">

                <div v-if="sizeSearch > 0">
                    <li v-for="(search, index) in sizeSearch" :key="index">
                        <input id="sdf" class="sizefull nav-search-modile" type="text" :placeholder="textPlaceholder[index]">
                    </li>
                </div>

               <div v-if="sizeListNav > 0">
                    <li v-for="(list, index) in textList" :key="index">
                        <button :id="`btn-list-${index}`" class="btn-nav-modile btn-list" @click="setStatusDetailList(index)">{{list}}</button>
                    </li>
                </div>

                <div v-if="showdetaillist === true && indexListSelect >= 0">
                    <li v-for="(value, index) in valueOption[indexListSelect]" :key="index">
                        <button class="btn-nav-modile btn-nav-modile2">{{value}}</button>
                    </li>
                </div>

                <div v-if="sizeBtnNav > 0">
                    <li v-for="(btn, index) in sizeBtnNav" :key="index">
                        <button v-if="checkDetailBtn(textBtnNav[index]) === false" class="btn-nav-modile">{{textBtnNav[index]}}</button>
                        <button v-else class="btn-nav-modile">
                            <i class="material-icons" style="font-size: 24px;">
                                {{classIcon}}
                            </i>
                        </button>
                    </li>
                </div>

            </ul>
        </div>
    </div>
</template>
<script>

import ButtonNav from '~/components/ButtonNav.vue'
import ListNav from '~/components/ListNav.vue'
import SearchNav from '~/components/SearchNav.vue'
export default {
    components: {
        ButtonNav,
        ListNav,
        SearchNav
    },

     props:['path','head','sizeBtnNav','textBtnNav',
    'sizeListNav','textList','valueOption','sizeSearch',
    'textSearch','textPlaceholder'],

    data(){
        return{
            classIcon:'',
            statusShowMenu: false,
            showdetaillist: false,
            indexListSelect: -1
        }
    },

    methods: {
        showListMenu(){
            if(this.statusShowMenu === false){
                this.statusShowMenu = true;
            }else{
                this.statusShowMenu = false;
            }
        },
        classize(s1,s2,s3){
          return s1+s2+s3
        },
        checkDetailBtn(text){
            let array = text.split('=>')
            if(array.length === 2){
                this.classIcon = `${array[1]}`
                return true;
            }else{
                return false;
            }
       },
       setStatusDetailList(index){
           if(this.showdetaillist === false){
               this.showdetaillist = true
               this.indexListSelect = index
           }else if(this.showdetaillist === true && this.indexListSelect === index){
               this.showdetaillist = false
               this.indexListSelect = -1
               document.getElementById(`btn-list-${index}`).style.backgroundColor = '#000'
           }
           
            
       }
    }
}
</script>
<style scoped>
.sizefull{
    width: 100%;
    height: 100%;
}
/*
.contro-flex-center{
    display:flex;
    justify-content: center;
}
.contro-flex-align-start{
    display:flex;
    justify-content: flex-start;
    align-items: center;
    background-color: rgb(0, 0, 0,0.5);
}

.box-search{
    width: 80%;
    height: 100%;
}
.box-search-icon{
    width: 20%;
    height: 100%;
}*/
.nav-search-modile{
    text-align: center;
    background-color: rgba(0, 0, 0,0.5);
    border: none;
    font-size: 14px;
    color: #fff;
}
.nav-search-modile:focus{
    background-color: rgb(0, 0, 0,0.8);
}
.nav-search-modile:focus::placeholder{
    color: rgb(255, 255, 255,0.8);
}
.nav-search-modile::placeholder {
  color: rgb(255, 255, 255,0.8);
}



.box-nav{
    width: 100%;
    height: 80px;
    padding: 0px 6%; 
    background-color: #f8f8f8;
    z-index: 500;
    border-bottom: 2px solid rgb(170, 170, 170);
}
.path-title{
    height: 40%;
    font-size: 14px;
    font-weight: 400;
}
.nav-detail{
    height: 60%;
    position: relative;
}
.head-title{
    
    width: fit-content;
    font-size: 25px;
    font-weight: 700;
    float: left;
}

label{
    margin: 0px;
}
.menu{
    position: absolute;
    right: 0px;
    width: fit-content;
    height: 100%;

    display: flex;
    justify-content: center;
    align-items: center;
}
.btn-menu{
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 0px;
    margin: 0px;

    background-color: rgb(0, 0, 0,0);
    border: none;
}
button,.btn-menu:focus{
    outline-width: 0px;
}
.material-icons{
    font-size: 40px;
}
.text-path-title, .head-title, .text-head-title,.search-nav{
    position: relative;
    top: 50%;
    left: 0%;
    transform: translate(0%, -50%);
}
.nav-list-menu{
    width: 100%;
    min-height: 100px;
    height: fit-content;
    position: fixed;
    top: 80px;
    animation-name: menuanimation;
    animation-duration: 0.5s;
}

@keyframes menuanimation {
    0% {
        position: fixed;
        top: -200px;
    }
    100% {
        position: fixed;
        top: 80px;
    }
  }

.list-menu{
    width: 100%;
    z-index: 5000;
    list-style: none;
    padding: 0;
    margin: 0;
    background-color: rgba(0, 0, 0,0.7);
}
.list-menu li{
    width: 100%;
    height: 60px;
    display: flex;
    justify-content: center;
    align-items: center;
}
.btn-nav-modile{
    width: 100%;
    height: 100%;
    padding: 0px;
    margin: 0px;

    background-color: black;
    border: none;
    font-size: 14px;
    color: #fff;

    display: flex;
    justify-content: center;
    align-items: center;
}
.btn-nav-modile2{
    
    
     width: 100%;
    height: 100%;
    padding: 0px;
    margin: 0px;

    background-color: rgb(255,255,255,0.7);
    border: none;
    font-size: 14px;
    color: rgb(65, 65, 65);


    display: flex;
    justify-content: center;
    align-items: center;
}

.btn-nav-modile:active{
    background-color: rgb(0, 0, 0,0.1);
    color: white;
}

.btn-list:focus{
    background-color: black;
}
</style>