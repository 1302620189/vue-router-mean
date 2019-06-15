<template>
    <div>
        <div class="page">
            <p>首页</p>
            <!-- <router-link to="/search">搜索</router-link> -->
            <div class="so">
                <input @click="goToSearch" placeholder="点击跳转搜索">              
            </div>

          <dl>
              <dt>
                  <img src="" alt="">
              </dt>
              <dd>
                <li v-for="(item,index) in list" :key="index" @click="goToShop(item.id)">{{item.title}}</li>
              </dd>
          </dl>
           <dl>
              <dt>
                  <img src="" alt="">
              </dt>
              <dd>
                <li v-for="(item,index) in list" :key="index" @click="goToShop(item.id)">{{item.title}}</li>
              </dd>
          </dl>

            <!-- <ul>
                <li v-for="(item,index) in list" :key="index" @click="goToShop(item.id)">{{item.title}}</li>
            </ul> -->
        </div>
        
        <my-footer></my-footer>
    </div>
</template>
<script>
// import myFooter from '../components/footer';
export default {
    props: {},
    components: {
        // myFooter
    },
    data() {
        return {
            list:[
                {
                    title:'本味轻食馆(二七店)',
                    id:1
                }
                //  {
                //     title:'蜀厢荣记麻辣烫(二七店)',
                //     id:2
                // },
                //  {
                //     title:'阿利茄汁面(医学院店)',
                //     id:3
                // }
            ]
        };
    },
    computed: {},
    methods: {
        goToSearch(){
            console.log('goToSearch');
            // this.$router.push('search'); 字符串
            // this.$router.push({path:'/search'}); 对象
            this.$router.push({path:'search',query:{val:'1111'}});//命名式路由跳转
            // this.$router.replace({name:'search'});//命名式路由跳转
        },
        goToShop(id){//动态路由在跳转的时候用name
            this.$router.push({name:'shop',params:{id:id}});
            // this.$router.push({path:'/shop/'+id});
        }
    },
    created() {
        console.log(this.$router,this.$route);
    },
    mounted() {}
};
</script>
<style scoped lang="">
.page{
    width:100%;
   height:100%;
   /* background:wheat; */
}
.page p{
    width:100%;
    height:50px;
    /* background:pink; */
    line-height:50px;
    text-align:center;
    /* border-bottom:1px solid #ccc; */
}
.so{
    width:100%;
    height:50px;
    line-height:50px;text-align:center;
}
input{
    width:80%;
    height:35px;
    padding:0 15px;
}
li{
    width:100%;
    height:50px;
    line-height:50px;
    margin:0 15px;
}
dl{
    width:100%;
    height:150px;
    display: flex;
    /* background:#ccc; */
}
dl dt{
    width: 130px;
    height:110px;
    background:pink;
    margin:15px 10px;
}
 dd {
     width:300px;
     margin:0 10px;
 }
</style>