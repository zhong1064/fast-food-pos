<template>
  <div class="pos">
    <el-row>
      <el-col :span="7" class="pos-order" id="order-list">
        <el-table :data="tableData" border style="width: 100%" show-summary>
          <el-table-column  prop="goodsName" label="商品" ></el-table-column>
          <el-table-column  prop="count" label="量" width="50"></el-table-column>
          <el-table-column prop="price" label="金额" width="70"></el-table-column>          
          <el-table-column fixed="right" label="操作" width="100">
            <template slot-scope="scope">
              <el-button @click="handleClick(scope.row)" type="text" size="small" >删除</el-button>
              <el-button type="text" size="small">增加</el-button>
            </template>
          </el-table-column>
        </el-table>
        <div class="pos-btn">
           <el-button type="warning">挂单</el-button>
           <el-button typr="dange">删除</el-button>
           <el-button type="success">结账</el-button>
        </div>
      </el-col>
      <el-col>我是产品11</el-col>
    </el-row>
  </div>
</template>

<script>
export default {
   data(){
      return {
         tableData: [{

          goodsName: '可口可乐',
          price: 8,
          count:1
        }, {

          goodsName: '香辣鸡腿堡',
          price: 15,
          count:1
        }, {

          goodsName: '爱心薯条',
          price: 8,
          count:1
        }, {

          goodsName: '甜筒',
          price: 8,
          count:1
        }]
      }
   },
  mounted() {
    let orderHeight = document.body.clientHeight;
    document.getElementById("order-list").style.height = orderHeight + "px";
  }
};
</script>

<style scoped>
.pos {
  color: #666;
}
.pos-order {
  background: #fff;
  border-right: 1px solid #eee;
}
.pos-btn {
   margin-top: 10px;
}
</style>