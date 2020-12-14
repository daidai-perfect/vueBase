<template>
  <div class="col-md-8">
    <h3 class="reply">评论回复：</h3>
    <h2 style='display: none'>暂无评论，点击左侧添加评论！！！</h2>
    <ul class="list-group">
      <Item 
      v-for='(comment,index) in coms' 
      :key="comment.id"
      :comment = 'comment'
      :addDelete='addDelete'
      :index = 'index'>
      </Item>
    </ul>
  </div>
</template>

<script>
import Item from './Item'
export default {
  name: '',
  components:{
    Item
  },
  props:['coms','addDelete']
}
</script>

<style scoped>
.reply {
  margin-top: 0px;
}
</style>
