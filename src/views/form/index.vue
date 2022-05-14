<template>
  <div class="app-container">
    <el-form ref="form" :model="form" label-width="120px">
      <el-form-item label="邮件题目">
        <el-input v-model="form.name" />
      </el-form-item>
      <el-form-item label="发件人">
        <el-input v-model="form.name" />
      </el-form-item>
      <el-form-item label="收件时间">
        <el-col :span="11">
          <el-date-picker v-model="form.date1" type="date" placeholder="Pick a date" style="width: 100%;" />
        </el-col>
      </el-form-item>
      <el-form-item label="邮件内容">
        <el-input v-model="form.desc" type="textarea" />
      </el-form-item>
      <el-form-item label="上传文件" prop="file">
        <el-upload
          class="upload-demo"
          drag
          action=""
          accept=".txt"
          :auto-upload="false"
          :file-list="form.file"
        >
          <i class="el-icon-upload" />
          <div class="el-upload__text"> <em /></div>
          <div slot="tip" class="el-upload__tip">只接受txt文件</div>
        </el-upload>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="onSubmit">上传</el-button>
        <el-button @click="onCancel">取消</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        name: '',
        region: '',
        date1: '',
        date2: '',
        delivery: false,
        type: [],
        resource: '',
        desc: ''
      }
    }
  },
  methods: {
    onSubmit() {
      this.$message('upload!')
    },
    onCancel() {
      this.$message({
        message: 'cancel!',
        type: 'warning'
      })
    }
  }
}
</script>

<style scoped>
.line{
  text-align: center;
}
</style>

