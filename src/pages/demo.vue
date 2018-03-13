<template>
  <div class="demo">
    <div class="list">
      <product></product>
        <check_list></check_list>
    </div>
     <div class="card">
       <div class="all">
         <div class="all-title" @click='checkall'>
            <i class="iconfont" :class="{'icon-yuanxingweixuanzhong-copy':!isallChecked,'icon-right-copy':isallChecked}"></i>
            全选
         </div>
           <div class="all-num">合计:{{totalPrice}}元</div>
       </div>
       <div class="des" @click='buy'>下单</div>
     </div>
  </div>
</template>
<script>
import check_list from "./index";
import product from "./product";
import info from "./info";
import {mapGetters,mapActions} from 'vuex'
export default {
  name: "demo",
  data() {
    return {
      total:0
    };
  },
  computed:{
     ...mapGetters(['totalPrice','totalNum','isallChecked']),
  },
  methods: {
    buy() {
     alert(this.totalPrice)
    },
      ...mapActions(['checkall']),
  },
  components: {
    check_list,
    product,
   

  }
};
</script>
<style lang='stylus' scoped>

.demo
  .card
    position: fixed;
    bottom: 0;
    width 100%
    height 50px
    line-height @height
    color #fff
    font-size 24px
    display flex
    .all
      flex 1
      color rgb(255,102,101)
      font-size 20px
      display flex
      .all-num
        padding-left 50px
      i
        margin-left 10px
      
    .des
      font-size 20px
      padding 0 30px
      background rgb(255,102,101)
</style>


