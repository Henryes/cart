<template>
  <section>
    <el-table ref="multiple" :data="tableData" tooltip-effect="dark" style="width: 100%">
      <el-table-column type="selection" width="55"></el-table-column>
      <el-table-column label="商品信息" width="120">
        <template>
          <div class="demo-fit">
            <div class="block" v-for="fit in fits" :key="fit">
              <span class="title">{{ fit }}</span>
              <el-avatar shape="square" :size="100" :fit="fit" :src="url"></el-avatar>
            </div>
          </div>
        </template>
      </el-table-column>
    </el-table>
  </section>
</template>
 
        <template slot-scope="scope">
  <span style="margin-left: 10px">{{ scope.row.date }}</span>
</template>
      </el-table-column>
      <el-table-column prop="name" label="商品数量" width="120">
        <template>
  <el-input v-model="search" placeholder="输入"></el-input>
</template>
      </el-table-column>
      <el-table-column prop="address" label="商品金额" show-overflow-tooltip></el-table-column>
      <el-input v-model="input" placeholder="请输入数量"></el-input>

      <el-table-column label="编辑">
        <template slot-scope="scope">
  <el-button size="mini" @input="handleEdit(scope.$index, scope.row)">编辑</el-button>
  <el-button size="mini" type="danger" @click="handleDelete(scope.$index, scope.row)">删除</el-button> 
</template>
      </el-table-column>
    </el-table>
  </section>
  
</template>

<script>
export default {
  data() {
    return {
      input: "",
      fits: ["fill", "contain", "cover", "none", "scale-down"],
      url:
        "https://fuss10.elemecdn.com/e/5d/4a731a90594a4af544c0c25941171jpeg.jpeg",
      tableData: [
        {
          date: "",
          name: "￥",
          address: "￥"
        },
        {
          date: "2016-05-04",
          name: "￥",
          address: "￥"
        },
        {
          date: "2016-05-01",
          name: "￥",
          address: "￥"
        },
        {
          date: "2016-05-03",
          name: "￥",
          address: "￥"
        }
      ]
    };
  },
  methods: {
    handleEdit(index, row) {
      console.log(index, row);
    },
    handleDelete(index, row) {
      console.log(index, row);
    }
  }
};
</script>
