<template>
  <div class="pos">
    <el-row>
      <el-col :span="7" class="pos-order" id="order-list">
        <el-table :data="tableData" border style="width: 100%" show-summary>
          <el-table-column prop="goodsName" label="商品"></el-table-column>
          <el-table-column prop="count" label="量" width="50"></el-table-column>
          <el-table-column prop="price" label="金额" width="70"></el-table-column>
          <el-table-column fixed="right" label="操作" width="100">
            <template slot-scope="scope">
              <el-button @click="handleClick(scope.row)" type="text" size="small">删除</el-button>
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
      <el-col :span="17">
        <div class="title">常用商品</div>
        <div class="often-goods-list">
          <ul>
            <li class="goods-item" v-for="item in  oftenGoods" :key="item.goodsId">
              <span>{{item.goodsName}}</span>
              <span class="o-price">￥{{item.price}}元</span>
            </li>
          </ul>
        </div>
        <div class="goods-type">
          <el-tabs  >
            <el-tab-pane label="汉堡" name="first">
               <div>
                 <ul class="cookList">
                   <li v-for="item in type0Goods " :key="item.id">
                     <span class="foodImg"><img src="http://7xjyw1.com1.z0.glb.clouddn.com/pos002.jpg" alt=""></span>
                     <span class="foodName">{{item.goodsName}}</span>
                     <span class="foodPrice">￥{{item.price}}元</span>
                   </li>
                 </ul>
               </div>
            </el-tab-pane>
            <el-tab-pane label="小食" name="second">配置管理</el-tab-pane>
            <el-tab-pane label="饮料" name="third">角色管理</el-tab-pane>
            <el-tab-pane label="套餐" name="fourth">定时任务补偿</el-tab-pane>
          </el-tabs>
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tableData: [
        {
          goodsName: "可口可乐",
          price: 8,
          count: 1
        },
        {
          goodsName: "香辣鸡腿堡",
          price: 15,
          count: 1
        },
        {
          goodsName: "爱心薯条",
          price: 8,
          count: 1
        },
        {
          goodsName: "甜筒",
          price: 8,
          count: 1
        }
      ],
      oftenGoods: [
        {
          goodsId: 1,
          goodsName: "香辣鸡腿堡",
          price: 18
        },
        {
          goodsId: 2,
          goodsName: "田园鸡腿堡",
          price: 15
        },
        {
          goodsId: 3,
          goodsName: "和风汉堡",
          price: 15
        },
        {
          goodsId: 4,
          goodsName: "快乐全家桶",
          price: 80
        },
        {
          goodsId: 5,
          goodsName: "脆皮炸鸡腿",
          price: 10
        },
        {
          goodsId: 6,
          goodsName: "魔法鸡块",
          price: 20
        },
        {
          goodsId: 7,
          goodsName: "可乐大杯",
          price: 10
        },
        {
          goodsId: 8,
          goodsName: "雪顶咖啡",
          price: 18
        },
        {
          goodsId: 9,
          goodsName: "大块鸡米花",
          price: 15
        },
        {
          goodsId: 20,
          goodsName: "香脆鸡柳",
          price: 17
        }
      ],
      type0Goods:[
          {
              goodsId:1,
              goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos001.jpg",
              goodsName:'香辣鸡腿堡',
              price:18
          }, {
              goodsId:2,
              goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos002.jpg",
              goodsName:'田园鸡腿堡',
              price:15
          }, {
              goodsId:3,
              goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos004.jpg",
              goodsName:'和风汉堡',
              price:15
          }, {
              goodsId:4,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos003.jpg",
              goodsName:'快乐全家桶',
              price:80
          }, {
              goodsId:5,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos003.jpg",
              goodsName:'脆皮炸鸡腿',
              price:10
          }, {
              goodsId:6,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos004.jpg",
              goodsName:'魔法鸡块',
              price:20
          }, {
              goodsId:7,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos001.jpg",
              goodsName:'可乐大杯',
              price:10
          }, {
              goodsId:8,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos003.jpg",
              goodsName:'雪顶咖啡',
              price:18
          }, {
              goodsId:9,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos002.jpg",
              goodsName:'大块鸡米花',
              price:15
          }, {
              goodsId:20,
               goodsImg:"http://7xjyw1.com1.z0.glb.clouddn.com/pos002.jpg",
              goodsName:'香脆鸡柳',
              price:17
          }

      ],
    };
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
.title {
  height: 20px;
  padding: 13px;
  text-align: left;
  border-bottom: 1px solid #D3DCE6;
  background:  #F9FAFC;
}
.goods-item {
  float: left;
  padding: 10px;
  margin: 5px;
  border: 1px solid #e5e9f2;
}
.o-price {
  color: #58b7ff;
}
.goods-type {
  clear: both;
  margin-left: 10px;
}
.cookList li {
  width: 23%;
  float: left;
  background: #fff;
  border: 1px solid #E5E9F2;
  margin: 2px;

}
.cookList li span{

        display: block;
        float:left;
   }
   .foodImg{
       width: 40%;
   }
   .foodName{
       font-size: 18px;
       padding-left: 10px;
       color:brown;

   }
   .foodPrice{
       font-size: 16px;
       padding-left: 10px;
       padding-top:10px;
   }
</style>