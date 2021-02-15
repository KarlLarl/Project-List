<template>
    <div>
        <div class="group">
            <div class="nav-mobile">
                <Navmobile 
                path="Project List" 
                head="Project List"
                :sizeBtnNav="sizeBtn"
                :textBtnNav="textBtnNav"
                :sizeListNav="sizeListNav"
                :textList="textList"
                :valueOption="valueOption"
                :sizeSearch="sizeSearch"
                :textSearch="textSearch"
                :textPlaceholder="textPlaceholder"/>
            </div>
    
            <div class="group-nav">
                <div class="nav-pc">
                    <Nav 
                        path="Project List" 
                        head="Project List"
                        :sizeBtnNav="sizeBtn"
                        :textBtnNav="textBtnNav"
                        :sizeListNav="sizeListNav"
                        :textList="textList"
                        :valueOption="valueOption"
                        :sizeSearch="sizeSearch"
                        :textSearch="textSearch"
                        :textPlaceholder="textPlaceholder"
                        @returnDataSearch="setDataSearch"/>
                </div>
            </div>

        <div class="group-contents">
            <div class="list-card" v-for="(card, index) in filterSearch" :key="index">
                <Card 
                :title="card.title" 
                :status="card.status" 
                :img="card.img" 
                :imgUser="card.imgUser" 
                :nameUser="card.nameUser" />
            </div>
        </div>

        <div class="box-content-modile">
            <div class="list-card-modile" v-for="(card, index) in filterSearch" :key="index">
                <Card 
                :title="card.title" 
                :status="card.status" 
                :img="card.img" 
                :imgUser="card.imgUser" 
                :nameUser="card.nameUser" />
            </div>
        </div>

    </div>
    </div>
</template>

<script>

import Card from '~/components/Card.vue'
import Nav from '~/components/Nav.vue'
import Navleft from '~/components/Navleft.vue'
import Navmobile from '~/components/Navmobile.vue'


export default {

    components: {
        Card,
        Nav,
        Navleft,
        Navmobile
    },

    data(){
        return {

            sizeBtn: 3,
            textBtnNav:['Add Project','displayicon=>autorenew','Logout'],

            sizeListNav: 1,
            textList:['เรียงตาม'],
            valueOption:[
                ['วันที่เริ่มโครงการ','วันที่แก้ไขโครงการ','วันที่เข้าดูโครงการ']
            ],

            sizeSearch: 1,
            textSearch:['ค้นหา'],
            textPlaceholder:['Search'],

            textSearchTitle:'',

            listCard:[
                {
                    title: 'Node JS',
                    img: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/bg%2Fnodejs.png?alt=media&token=dc4a3835-da37-43e5-9241-9c83bba1ab24',
                    imgUser: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/User%2FMonkey%20D.%20Luffy.png?alt=media&token=84896f23-a028-4170-bfa2-e9067c3a01be',
                    nameUser: 'Monkey D. Luffy',
                    status: 'กัปตัน'
                },
                {
                    title: 'Angular JS',
                    img: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/bg%2FAngular.jpg?alt=media&token=228a4ca1-7bb4-4841-bed8-256a406a4bd4',
                    imgUser: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/User%2FRoronoa%20zoro.jpg?alt=media&token=2dd995cc-9c20-4af8-b365-22badba1269a',
                    nameUser: 'Roronoa zoro',
                    status: 'นักดาบประจำเรือ'
                },
                {
                    title: 'Docker',
                    img: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/bg%2Fdocker.png?alt=media&token=25b61a10-ea78-4272-bff4-c43667cf3185',
                    imgUser: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/User%2FNAMI.png?alt=media&token=c434b4b6-7792-4fe5-8218-55ca93cc876c',
                    nameUser: 'Nami',
                    status: 'ต้นหนเรือ'
                },
                {
                    title: 'React',
                    img: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/bg%2Freact.png?alt=media&token=e4209c77-be57-44da-b300-2ba182712030',
                    imgUser: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/User%2FUsopp.png?alt=media&token=b6ba3d83-885d-4fa8-ab8c-5df118498ae7',
                    nameUser: 'Usopp',
                    status: 'พลปืนประจำเรือ'
                },
                {
                    title: 'VUE JS',
                    img: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/bg%2Fvue.jpg?alt=media&token=d1d21c12-1f37-4349-be74-9d842b0f51d6',
                    imgUser: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/User%2FSanji.jpg?alt=media&token=cb5a29d0-8b03-4ab6-a550-a4e491c49340',
                    nameUser: 'Sanji',
                    status: 'พ่อครัวประจำเรือ'
                },
                {
                    title: 'IONIC',
                    img: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/bg%2Fionic.jpg?alt=media&token=cf8a7635-1288-4484-af8b-ce1afa225187',
                    imgUser: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/User%2Fchopper.jpg?alt=media&token=9b714c5f-8c8f-4853-935a-7fba6dfcb8c0',
                    nameUser: 'Tony Tony Chopper',
                    status: 'หมอประจำเรือ'
                },
                {
                    title: 'Visual Studio',
                    img: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/bg%2FcsCode.jpeg?alt=media&token=3d1803b9-7d09-4b16-b221-272b57f8e0ed',
                    imgUser: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/User%2FNico%20Robin.jpg?alt=media&token=ded04ae5-6896-4f24-9e81-4b6acfb8caed',
                    nameUser: 'Nico Robin',
                    status: 'นักโบราณคดีประจำเรือ'
                },
                {
                    title: 'Python',
                    img: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/bg%2Fpython.jpg?alt=media&token=7bac5119-be3c-4bf2-9d61-fe9a04c9c468',
                    imgUser: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/User%2FFranky.png?alt=media&token=5d0f1336-a8b6-4ccf-8b77-3499ffb5e8cf',
                    nameUser: 'Franky',
                    status: 'ช่างซ่อมประจำเรือ'
                },
                {
                    title: 'JAVA',
                    img: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/bg%2FJava.jpg?alt=media&token=c616b771-9b5d-44bc-a7a9-7d2fd204c6c0',
                    imgUser: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/User%2FHamming%20Brook.jpg?alt=media&token=bea281ae-0fce-46e2-97be-1e000a28d1e0',
                    nameUser: 'Hamming Brook',
                    status: 'นักดนตรีประจำเรือ'
                },
                {
                    title: 'Application Coding',
                    img: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/bg%2Fad_ap.png?alt=media&token=074d2532-300f-4082-9ad5-05dc83a654fc',
                    imgUser: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/User%2FMonkey%20D.%20Luffy.png?alt=media&token=84896f23-a028-4170-bfa2-e9067c3a01be',
                    nameUser: 'Monkey D. Luffy',
                    status: 'กัปตัน'
                },
                {
                    title: 'Cloud Server',
                    img: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/bg%2Fcloud.jpg?alt=media&token=f44638b5-d10a-4feb-8244-8b76f982716d',
                    imgUser: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/User%2FRoronoa%20zoro.jpg?alt=media&token=2dd995cc-9c20-4af8-b365-22badba1269a',
                    nameUser: 'Roronoa zoro',
                    status: 'นักดาบประจำเรือ'
                },
                {
                    title: 'Blockchain',
                    img: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/bg%2Fblockchain.jpg?alt=media&token=7e834657-fc3b-4870-87f7-3bb3353607a1',
                    imgUser: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/User%2FSanji.jpg?alt=media&token=cb5a29d0-8b03-4ab6-a550-a4e491c49340',
                    nameUser: 'Sanji',
                    status: 'พ่อครัวประจำเรือ'
                },
                {
                    title: 'libra',
                    img: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/bg%2Flibra.png?alt=media&token=6c410f39-a285-418c-b145-867f1657ecd1',
                    imgUser: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/User%2FNAMI.png?alt=media&token=c434b4b6-7792-4fe5-8218-55ca93cc876c',
                    nameUser: 'Nami',
                    status: 'ต้นหนเรือ'
                },
                {
                    title: 'COBOL',
                    img: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/bg%2FCOBOL.jpg?alt=media&token=f0295ce1-ce40-4981-9ffa-8aec9b68684f',
                    imgUser: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/User%2FMonkey%20D.%20Luffy.png?alt=media&token=84896f23-a028-4170-bfa2-e9067c3a01be',
                    nameUser: 'Monkey D. Luffy',
                    status: 'กัปตัน'
                },
                {
                    title: 'Spring Boot',
                    img: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/bg%2FSpring-Boot.png?alt=media&token=030e2cd1-5bce-49b5-8dc3-162138b0dbc4',
                    imgUser: 'https://firebasestorage.googleapis.com/v0/b/intern-d961b.appspot.com/o/User%2FUsopp.png?alt=media&token=b6ba3d83-885d-4fa8-ab8c-5df118498ae7',
                    nameUser: 'Usopp',
                    status: 'พลปืนประจำเรือ'
                }
            ]
        }
    },
    methods: {
       setDataSearch(data){
           console.log(data)
           this.textSearchTitle = data
       }
    },
    computed:{
        filterSearch(){
            if(this.textSearchTitle === ''){
                return this.listCard
            }else{
                return this.listCard.filter((card,i) => {
                    return card.title.includes(this.textSearchTitle)
                })
            }   
        },
    }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Prompt:100,200,400,500,600,700&display=swap');

*{font-family: 'Prompt', sans-serif;}

body{
    background-color: #f8f8f8;
}

.nav-mobile{
    position: fixed;
    top: 0px;
    left: 0px;
    z-index: 10;
    width: 100vw;
}

.group{
    width: 100%;
    height: auto;
}

.group-nav{
    margin-bottom: 15px;
    width: 100%;
}
.list-card{
    margin-bottom: 10px;
    margin-right: 10px;
    margin-left: 10px;
}

.group-contents{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    margin-top: 100px;
}

@media screen and (min-width: 1201px) {
/*หน้าจอใหญ่*/
    .nav-pc{display: block;}
    .nav-mobile{display: none;}
    .box-content-modile{display: none;}
    .group{padding: 0% 4%;}
    .group-contents{margin-top: 0px;}
}

@media screen and (max-width: 1200px) {
/*หน้าจอกลาง*/
    .nav-pc{display: none;}
    .nav-mobile{display: block;}
    .box-content-modile{display: none;}
    .group{padding: 0% 4%;}
}

@media screen and (max-width: 500px) {
/*หน้าจอเล็ก*/
    .nav-pc{display: none;}
    .nav-mobile{display: block;}
    .box-content-modile{display: block;}
    .group{padding: 0px;}
    .list-card{width: fit-content;}
    .group-contents{display: none;}
    .list-card{
        margin-bottom: 10px;
        width: 100%;
    }
    .box-content-modile{
        padding-left: 10%;
        padding-right: 10%;
        margin-top: 100px;
    }
    .box-content-modile .list-card-modile{
        margin-bottom: 15px;
    }
}
</style>