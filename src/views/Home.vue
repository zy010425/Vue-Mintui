<template>
  <div class="container px-2">
 <!-- 微信头部标题行 -->
 <titlebar :leftTitle="leftTitle"></titlebar>
    <mt-tab-container name="有几个面板" v-model="selected" class="py-5">
      <mt-tab-container-item id="微信">
       <messagelist></messagelist>
      </mt-tab-container-item>
      <mt-tab-container-item id="通讯录">
        <mt-field label="用户名" placeholder="请输入用户名" v-model="username"></mt-field>
        <mt-field label="邮箱" placeholder="请输入邮箱" type="email" v-model="email"></mt-field>
        <mt-field label="密码" placeholder="请输入密码" type="password" v-model="password"></mt-field>
        <mt-field label="手机号" placeholder="请输入手机号" type="tel" v-model="phone"></mt-field>
        <mt-field label="网站" placeholder="请输入网址" type="url" v-model="website"></mt-field>
        <mt-field label="数字" placeholder="请输入数字" type="number" v-model="number"></mt-field>
        <mt-field label="自我介绍" placeholder="自我介绍" type="textarea" rows="4" v-modal="introduction"></mt-field>

        <mt-field label="邮箱" state="success" v-model="email"></mt-field>
        <mt-field label="邮箱" state="error" v-model="email"></mt-field>
        <mt-field label="邮箱" state="warning" v-model="email"></mt-field>

        <mt-button @click.native="closeLoading" type="primary">关闭加载</mt-button>
      </mt-tab-container-item>
      <mt-tab-container-item id="发现">
        <mt-cell v-for="n in 27" :key="n" title="tab-container 发现"></mt-cell>
      </mt-tab-container-item>
    </mt-tab-container>

    <mt-tabbar name="底部导航按钮" v-model="selected" fixed>
      <mt-tab-item id="微信">
        <img slot="icon" src="@/assets/img/ic_weixin_normal.png" />
        微信
      </mt-tab-item>
      <mt-tab-item id="通讯录">
        <img slot="icon" src="@/assets/img/ic_contacts_normal.png" />
        通讯录
      </mt-tab-item>
      <mt-tab-item id="发现">
        <img slot="icon" src="@/assets/img/ic_find_normal.png" />
        发现
      </mt-tab-item>
      <mt-tab-item id="我">
        <img slot="icon" src="@/assets/img/ic_me_normal.png" />
        我
      </mt-tab-item>
    </mt-tabbar>
  </div>
</template>

<script>
//引入json文件->js object   list就是一个js对象
import list from "@/assets/json/messagelist.json";
import TitleBar from "@/components/weixin/TitleBar.vue";
import MessageList from "@/components/weixin/MessageList.vue";
// console.log("list对象的输出：")
// console.log(list.data)

export default {
  data() {
    return {
      selected: "微信", //选中的是哪个导航按钮
      rows: list.data, //微信消息列表数据，来源是json文件
      leftTitle:"微信(39)",

      //下面这些仅仅是测试用
      username: "",
      email: "",
      password: "",
      phone: "",
      website: "",
      number: "",
      introduction: ""
    };
  },
   methods: {
     mysearch(){
       this.$toast("搜索功能，待实现....")
     },
     myadd(){
        this.$toast("搜索功能，待实现....")
     }
   },
   components:{
    titlebar:TitleBar,
    messagelist: MessageList,
  }


};
</script>
