<template>
  <div class="col-md-4">
    <form class="form-horizontal">
      <div class="form-group">
        <label>用户名</label>
        <input type="text" class="form-control" placeholder="用户名" v-model = 'username'>
      </div>
      <div class="form-group">
        <label>评论内容</label>
        <textarea class="form-control" rows="6" placeholder="评论内容"
        v-model="comment"></textarea>
      </div>
      <div class="form-group">
        <div class="col-sm-offset-2 col-sm-10">
          <button type="button" class="btn btn-default pull-right" @click = 'addC'>提交</button>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: '',
  data(){
    return{
      username:'',
      comment:''
    }
  },
  props:['addComment'],
  methods:{
    addC(){
      // 获取输入内容
      let{username,comment} = this

      if(username.trim()&&comment.trim()){
        // 将内容转换成对象
        let id = Date.now()
        let obj = {
          id,
          username,
          comment
        }
        console.log(obj)
        // 添加到列表展示
        this.addComment(obj)
      }else{
        alert('请输入格式正确的用户名字和内容!')
      }

      this.username = ''
      this.comment = ''



      
    }
  }
}
</script>

<style scoped>

</style>
