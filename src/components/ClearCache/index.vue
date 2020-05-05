<template>
  <div>
    <el-tooltip class="item" effect="dark" content="清除缓存" placement="bottom">
      <svg-icon icon-class="clear" @click="clear" />
    </el-tooltip>

  </div>
</template>

<script>
import { clearCache } from '@/api/tools'
export default {
  name: 'ClearCache',
  props: {},
  data() {
    return {}
  },
  created() {},
  mounted() {},
  methods: {
    clear() {
      this.$confirm('是否清除缓存', '提示', {
        confirmButtonText: '确定',
        cancelButtonText: '取消',
        type: 'warning'
      }).then(() => {
        clearCache().then(response => {
          this.$message({
            type: 'success',
            message: '删除成功!'
          })
        })
      }).catch(() => {})
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
