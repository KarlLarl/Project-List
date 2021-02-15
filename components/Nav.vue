<template>
    <div class="box-nav">
        <div class="path-title">
            <label class="text-path-title">{{path}}</label>
        </div>
        <div class="nav-detail">
            <div class="head-title">
                <label class="text-head-title">{{head}}</label>
            </div>
            <div class="menu">
                <div class="groupDetail">
                    <div class="float">
                        <div 
                        :v-if="sizeSearch > 0" 
                        class="search-nav" 
                        v-for="(search, index) in sizeSearch" 
                        :key="index">
                            <SearchNav 
                            :textSearch="textSearch[index]" 
                            :textPlaceholder="textPlaceholder[index]" 
                            @setSearch="setSearchAndReturn"/>
                        </div>
                    </div>
                    <div class="float">
                        <div :v-if="sizeListNav > 0" 
                            class="list-nav" 
                            v-for="(list, index) in sizeListNav" 
                            :key="index">
                            <ListNav 
                            :textList="textList[index]" 
                            :valueOption="valueOption[index]"/>
                        </div>
                    </div>
                    <div class="float">
                        <div :v-if="sizeBtnNav > 0" 
                            class="btn-nav" v-for="(btn, index) in sizeBtnNav" 
                            :key="index">
                            <ButtonNav 
                            :textBtn="textBtnNav[index]"/>
                        </div>
                    </div>
                </div>
                
            </div>
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

    methods: {
       setSearchAndReturn(data){
           this.$emit('returnDataSearch',data)
       }
    },
}
</script>
<style scoped>
.box-nav{
    width: 100%;
    height: 120px;
    background-color: #f8f8f8;
    z-index: 100;
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
    font-size: 40px;
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
}
.groupDetail,.btn-nav,.list-nav,.text-path-title, .head-title, .text-head-title,.search-nav{
    position: relative;
    top: 50%;
    left: 0%;
    transform: translate(0%, -50%);
}
.btn-nav,.list-nav,.search-nav{
    float: left;
    margin-left: 5px;
    margin-right: 5px;
}
.float{
    float: left;
}
</style>