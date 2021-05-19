<template>
  <div>
        <div
          v-for="(item,i) in rows"
          :key="i"
          class="row py-1"
          style="border-bottom:1px solid #d9d9d9"
        >
          <!-- 1左侧1个图片 -->
          <div class="col-2">
            <img :src="require(`@/assets/img/${item.img}`)" width="50" height="50" class="rounded" />
          </div>
          <!-- 2中间标题和子标题 -->
          <div class="col-8 text-left text-truncate">
            <div class="font-weight-bold">{{item.title}}</div>
            <div class="text-muted">{{item.subtitle}}</div>
          </div>
          <!-- 3时间-->
          <div class="col-2"> {{item.time}}</div>
        </div>
  </div>
</template>

<script>
import list from "@/assets/json/messagelist.json";
export default {
 data() {
    return {
      rows: list.data, //微信消息列表数据，来源是json文件
    };
  },
}
</script>

<style>

</style>