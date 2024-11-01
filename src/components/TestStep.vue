<template>
  <el-card :bordered="false">
    <el-steps :active="2" align-center>
      <el-step
        v-for="(item, index) in stepList"
        :key="index"
        :title="item.title"
        :description="item.description"
        class="stepItem"
      >
        <template #icon>
          <div class="stepNum">{{ index + 1 }}</div>
          <el-progress
            class="progress"
            type="circle"
            :show-text="false"
            :stroke-width="10"
            :percentage="item.range"
          ></el-progress>
        </template>
      </el-step>
    </el-steps>
  </el-card>
</template>

<script>
export default {
  name: "TestStep",
  data() {
    return {
      stepList: [
        {
          title: "步骤1",
          description: "这是一段描述性文字",
          range: 0,
        },
        {
          title: "步骤2",
          description: "这是一段描述性文字",
          range: 25,
        },
        {
          title: "步骤3",
          description: "这是一段描述性文字",
          range: 50,
        },
        {
          title: "步骤4",
          description: "这是一段描述性文字",
          range: 75,
        },
        {
          title: "步骤5",
          description: "这是一段描述性文字",
          range: 100,
        },
      ],
    };
  },
};
</script>

<style scoped lang="less">
.stepItem {
  ::v-deep .el-step__icon {
    background-color: #fff;
    position: relative;
  }
}
.stepNum {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 9;
}
.progress {
  ::v-deep .el-progress-circle {
    width: 26px !important;
    height: 26px !important;
  }
}
</style>