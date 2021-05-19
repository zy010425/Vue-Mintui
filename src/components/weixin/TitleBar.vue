<template>
    <div
      name="头部标题行"
      class="row bg-dark text-white align-items-center fixed-top px-2"
      style="height:48px"
    >
      <div class="col-8 h5 text-left" style="margin-bottom: 0px;">{{leftTitle}}</div>
      <div class="col-4 d-flex flex-row justify-content-end">
        <div class="pr-2">
          <img src="@/assets/img/ic_search.png" width="24" height="24" @click="search" />
        </div>
        <div>
          <img src="@/assets/img/ic_add.png" width="24" height="24" @click="add"/>
        </div>
      </div>
    </div> 
</template>

<script>
export default {
 props:{
    //  左边标题文字
    leftTitle:{default:""},
    //2个方法
    add:{type:Function},
    search:{type:Function},
 }
}
</script>

<style>

</style>