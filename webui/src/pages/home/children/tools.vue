<template>
  <div class="site-mix" style="color: #dde6f9">
    <el-tabs v-model="activeName" type="card" @tab-click="handleTabsClick">
      <el-tab-pane label="网络测试" name="network-test">
      </el-tab-pane>
      <el-tab-pane label="MT 登录" name="login-mteam">
      </el-tab-pane>
      <el-tab-pane label="链接" name="link">
      </el-tab-pane>
      <el-tab-pane label="修改 hosts" name="hosts">
      </el-tab-pane>
      <el-tab-pane label="http 代理" name="proxy">
      </el-tab-pane>
      <el-tab-pane label="批量链接" name="bulk-link">
      </el-tab-pane>
    </el-tabs>
    <router-view style="height: calc(var(--vh, 1vh) * 100 - 156px); overflow: auto;"></router-view>
  </div>
</template>

<script>
export default {
  data () {
    return {
      activeName: 'network-test'
    };
  },
  methods: {
    handleTabsClick (param) {
      this.$goto('/tools/' + this.activeName, this.$router);
    }
  },
  async mounted () {
    this.activeName = this.$route.path.split('/').pop();
  }
};
</script>

<style scoped>
</style>
