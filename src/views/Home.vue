<template>
  <div class="row bg-dark text-white align-items-center" style="height:48px">
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
</template>

<script>

export default {
  data(){
    return{
      selected:"微信",//选中的是哪个导航按钮
    }
  }
  
}
</script>
