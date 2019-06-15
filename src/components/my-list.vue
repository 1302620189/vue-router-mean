<template>
    <div class="listcontent">
        <h3>{{name}}</h3>
        <dl v-for="(item,index) in foods" :key="index">
            <dt>
                <img :src="item.image" alt="">
            </dt>
            <dd>
                <span>{{item.name}}</span>
                <span>{{item.description}}</span>
                <span>￥{{item.price}}</span>
            </dd>
        </dl>
    </div>
</template>
<script>
export default {
    props:['name','foods'],
    components:{

    },
    data(){
        return {

        }
    },
    computed:{

    },
    methods:{

    },
    created(){

    },
    mounted(){

    }
}
</script>
<style scoped lang="">
dl{
    display: flex;
}
dl dt{
    width: 110px;
    height:110px;
}
dl dt img{
    height: 100px;
    width: 100px;
    margin:0 10px;
 }
 h3{
     width:100%;
     height:40px;
     line-height:40px;
     margin:0 15px;
     font-size:16px;
 }
 dd {
     width:100px;
     margin:0 10px;
 }
 dd span{
     display:block;
     width: 120px;
     height:20px;
     margin:10px 5px;
 }
 dd span:nth-child(2){
    color:#888;
 }
 dd span:nth-child(3){
     font-size:18px;
     color:red;
 }
</style>