<template>
  <div class="container px-2">
    <!-- 微信头部把标题 -->
    <titlebar :leftTitle="leftTitle" :add="myadd" :search="mysearch"></titlebar>
    <mt-tab-container name="有几个面板" v-model="selected" class="py-5">
      <mt-tab-container-item id="微信">        
        <messagelist></messagelist>
      </mt-tab-container-item>
      <mt-tab-container-item id="通讯录">
        <h5>这是“通讯录”面板，待完成。。。。</h5>        
      </mt-tab-container-item>
      <mt-tab-container-item id="发现">  
        <router-view></router-view>
      </mt-tab-container-item>
    </mt-tab-container>
    <!-- 底部导航 -->
    <mt-tabbar name="底部导航按钮" v-model="selected" fixed>
      <mt-tab-item id="微信">
        <img
          slot="icon"
          :src="tabbarSelected[0] ? require('@/assets/img/ic_weixin_selected.png'):require('@/assets/img/ic_weixin_normal.png')"
        />
        微信
      </mt-tab-item>
      <mt-tab-item id="通讯录">
        <img
          slot="icon"
          :src="tabbarSelected[1] ? require('@/assets/img/ic_contacts_selected.png'):require('@/assets/img/ic_contacts_normal.png')"
        />
        通讯录
      </mt-tab-item>
      <mt-tab-item id="发现">
        <img
          slot="icon"
          :src="tabbarSelected[2] ? require('@/assets/img/ic_find_selected.png'):require('@/assets/img/ic_find_normal.png')"
        />
        发现
      </mt-tab-item>
      <mt-tab-item id="我">
        <img
          slot="icon"
          :src="tabbarSelected[3] ? require('@/assets/img/ic_me_selected.png'):require('@/assets/img/ic_me_normal.png')"
        />
        我的
      </mt-tab-item>
    </mt-tabbar>
  </div>
</template>

<script>


import TitleBar from "@/components/weixin/TitleBar.vue";
import MessageList from "@/components/weixin/MessageList.vue";

export default {
  data() {
    return {
      selected: "微信", // 选中的     
      leftTitle: "微信（39）",

      tabbarSelected: [true, false, false, false], //是否选中这个底部导航标签

      
    };
  },

  methods: {
    mysearch() {
      this.$toast("搜索功能待实现。。。。。");
    },

    myadd() {
      this.$toast("添加功能待实现");
    },

    
  },
  // created(){
  // //   Indicator.open({
  // //   text: '加载中...',
  // //   spinnerType: 'fading-circle'
  // // })
  // // setTimeout(()=>{
  // //   this.closeLoading()
  // // },3000)
  // },
  //    updated(){
  //      //this.$toast("你选中了"+this.selected)
  //    },
  //    methods(){
  //     //  closeLoading(){

  //     //  }
  //    },
  components: {
    titlebar: TitleBar,
    messagelist: MessageList,   
    
  },

  watch: {
    selected() {
      //this.$toast(this.selected);
      this.tabbarSelected = [false, false, false, false]; //设置都没有被选中
      switch (this.selected) {
        case "微信":
          this.tabbarSelected[0] = true;
          break;
        case "通讯录":
          this.tabbarSelected[1] = true;
          break;
        case "发现":
          this.tabbarSelected[2] = true;
          this.$router.push("/login")
          break;
        case "我":
          this.tabbarSelected[3] = true;
          break;
        default:
          break;
      }
    }
  }
};
</script>
<style  scoped>
.mint-tabbar > .mint-tab-item.is-selected {
  background-color: transparent;
  color: #26e452;
}
</style>