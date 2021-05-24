<template>
  <!-- 弹性布局 -->
  <div>
    <div v-for="(item,i) of list" :key="i">
      <!-- 商品图片 -->
      <div>
        <img :src="`${baseURL}/${item.pic}`"/>
      </div>
      <!-- 商品名称 -->
      <div>{{item.title}}</div>
      <!-- 商品价格 -->
      <div>￥{{item.price}}</div>
      <!-- 加入购物车 -->
      <div><mt-button>加入购物车</mt-button></div>
    </div>
  </div>
</template>

<script>
import { getProductList,baseURL } from "@/assets/js/apis/product.js";
export default {
  data() {
    return {
      list: [], //保存服务器返回的商品列表数据

      baseURL:baseURL,
    };
  },
  mounted() {
    this.loadMore();
  },
  methods: {
    async loadMore() {
      let result = await getProductList();
      //console.log(result);
      this.list = result.data; //返回商品列表数据保存到数组
    }
  }
  // components:{
  //   getproductlist:getProductList
  // }
};
</script>

<style>
</style>