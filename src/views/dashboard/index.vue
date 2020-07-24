<template>
  <div class="dashboard-container">
    <!--搜索框-->
    <el-form :inline="true"  class="demo-form-inline" >
      <el-form-item label="审批人">
        <el-input  placeholder="审批人"></el-input>
      </el-form-item>
      <el-form-item label="活动区域">
        <el-select  placeholder="活动区域">
          <el-input  placeholder="审批人"></el-input>
        </el-select>
      </el-form-item>
      <el-form-item>
        <el-button type="primary">查询</el-button>
      </el-form-item>
    </el-form>
    <div style="float:right" >
      <text>豆瓣评分</text>
      <el-rate disabled show-score text-color="#ff9900" value=4 score-template="8"></el-rate>
    </div>
    <!--轮播图-->
    <el-carousel :interval="4000" type="card" height="600px" width="600px" style ="margin-top: 80px;">
      <el-carousel-item v-for="item in 6" :key="item">
        <h3 class="medium">{{ item }}</h3>
      </el-carousel-item>
    </el-carousel>
    <!--播放条-->
    <audio controls="controls" ref='audio' :src="musicUrl" style="width:100%;height:100px;"></audio>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  name: 'Dashboard',
  computed: {
    ...mapGetters([
      'name'
    ])
  }
}
</script>

<style lang="scss" scoped>
.dashboard {
  &-container {
    margin: 30px;
  }
  &-text {
    font-size: 30px;
    line-height: 46px;
  }
}

.el-carousel__item h3 {
  color: #475669;
  font-size: 14px;
  opacity: 0.75;
  line-height: 200px;
  margin: 0;
}

.el-carousel__item:nth-child(2n) {
  background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n+1) {
  background-color: #d3dce6;
}
</style>
