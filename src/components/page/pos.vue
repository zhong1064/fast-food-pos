<template>
   <div class="pos">
       <el-row>
          <el-col :span="7" class="pos-order" id="order-list">
             我的订单
          </el-col>
           <div>
              11
               <el-col>
             我是产品11
          </el-col>
           </div>
       </el-row>
   </div>
</template>

<script>
export default {
  mounted(){
    let orderHeight = document.body.clientHeight
    document.getElementById('order-list').style.height = orderHeight+'px'
  }
}
</script>

<style scoped>
.pos {
   color: #666;
}
.pos-order {
     background: #fff;
     border-right: 1px solid #666;
     
 }
</style>