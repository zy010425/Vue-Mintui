<template>
  <div class="container px-2">
    <div name="头部标题行" class="row bg-dark text-white align-items-center" style="height:48px">
      <div class="col-8 h5 text-left" style="margin-bottom: 0px;">微信(90)</div>
      <div class="col-4 d-flex flex-row justify-content-end">
        <div class="pr-2">
          <img src="@/assets/img/ic_search.png" width="24" height="24" />
        </div>
        <div>
          <img src="@/assets/img/ic_add.png" width="24" height="24" />
        </div>
      </div>
    </div>

    <mt-tab-container name="有几个面板" v-model="selected">
      <mt-tab-container-item id="微信">
        <mt-cell v-for="n in 20" :key="n" title="tab-container 微信"></mt-cell>
      </mt-tab-container-item>
      <mt-tab-container-item id="通讯录">
        <mt-cell v-for="n in 25" :key="n" title="tab-container 通讯录"></mt-cell>
      </mt-tab-container-item>
      <mt-tab-container-item id="发现">
        <mt-cell v-for="n in 27" :key="n" title="tab-container 发现"></mt-cell>
      </mt-tab-container-item>
    </mt-tab-container>

    <mt-tabbar name="底部导航按钮" v-model="selected" fixed>
      <mt-tab-item id="微信">
        <img slot="icon" src="@/assets/img/ic_weixin_normal.png" />
        外卖
      </mt-tab-item>
      <mt-tab-item id="通讯录">
        <img slot="icon" src="@/assets/img/ic_contacts_normal.png" />
        订单
      </mt-tab-item>
      <mt-tab-item id="发现">
        <img slot="icon" src="@/assets/img/ic_find_normal.png" />
        发现
      </mt-tab-item>
      <mt-tab-item id="我">
        <img slot="icon" src="@/assets/img/ic_me_normal.png" />
        我的
      </mt-tab-item>
    </mt-tabbar>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  data(){
    return{
      selected:"微信",// 选中的
    }
  },

   updated(){
     this.$toast("你选中了")
   }
};
</script>
<style  scoped>
</style>
