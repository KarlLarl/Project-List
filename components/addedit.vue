<template>
    <div>
        <div v-if="path === 'edit-project'">
            <div class="popcard">
                <div >
                    <div>
                        <div>
                            Select Project :  
                            <select class="select-op" >
                                <option value="TEST">Please select</option>
                            </select>
                        </div>


                        <div class="mar-top">
                            <a>Project Name : </a>  
                            <input class="input-pname" type="text" v-model="proname">
                        </div>

                        <div class="mar-top">
                            Image : <button  class="img-txt"></button>
                                        
                        </div>

                    </div>
                    <!-- Top -->
                    <!-- Down  -->
                    <div>
                        <div class="mar-top">
                            Project Detail : 
                        </div>
                        <div>
                            <textarea contenteditable="true" class="detailtxt" v-model="prodetail"></textarea>
                        </div>
                    <!-- Down -->
                    </div>
                </div>
                <div class="btn">
                    <button class="cancel" type="submit">Cancel</button>
                    <button class="submit" type="submit">Submit</button>
                </div>
            </div>
        </div>
        <div v-if="path === 'add-project'">
            <div class="popcard">
                <div >
                    <div>
                        <div class="mar-top">
                            <a>Project Name : </a>  
                            <input class="input-pname" type="text" v-model="proname">
                        </div>

                        <div class="mar-top">
                            Image : <button  class="img-txt"></button>
                                        
                        </div>

                    </div>
                    <!-- Top -->
                    <!-- Down  -->
                    <div>
                        <div class="mar-top">
                            Project Detail : 
                        </div>
                        <div>
                            <textarea contenteditable="true" class="detailtxt" v-model="prodetail"></textarea>
                        </div>
                    <!-- Down -->
                    </div>
                </div>
                <div class="btn">
                    <button class="cancel" type="submit">Cancel</button>
                    <button class="submit" type="submit">Submit</button>
                </div>
            </div>
        </div>
    </div>
</template>



<script>
export default {
    data(){
        return{
            path: ''
        }  
    }
    ,mounted(){
        this.path = this.$route.name
    }
    
}
</script>

<style lang="scss" scoped>
.popcard{
    background-color: rgb(255, 255, 255);
    box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
    width: fit-content;
    height: fit-content;
    border: 2px solid #F56868;
    border-radius: 0 6px 6px 6px;
    padding: 25px;
    margin-top: -2px;
    font-weight: bold;
    color: #5F5F5F;
  
        .detailtxt{
            height: 250px;
            width: 560px;
            margin-top: 10px;
            border-radius: 4px;
           
        }

    .btn{
        margin-top: 50px;
    }
        button{
            padding: 10px;
            font-weight: bold;
            border-radius: 4px;
        }
        .cancel{
            background-color: white;
            border: 1px solid #F56868; 
        }
        .submit{
            background-color: #F56868;
            border: 1px ;
            color: white;
            margin-left: 420px;
            
        }
    input{
        width: 175px;
        height: 25px
    }
    .img-txt{
        border-radius: 4px;
        width: 25px;
        height: 25px;
        border: 1px solid #E5E5E5;
        background-color: rgb(255, 255, 255);
        background-image: url('~assets/paperclip.png');
        background-size: cover;
        background-repeat: no-repeat;

    }
}
.input-pname{
    border-radius: 4px;
    border: 1px solid #E5E5E5;
}
.mar-top{
    margin-top: 10px;

}
.select-op{
    border-radius: 4px;
    width: 175px
}

</style>
