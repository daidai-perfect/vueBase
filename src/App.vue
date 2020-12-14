<template>
  <div>
    <Header></Header>
    <div class="container">
      <Add :addComment = 'addComment'></Add>
      <List :coms='comments' :addDelete='addDelete'></List>
    </div>
  </div>
</template>

<script>
import Header from './components/Header'
import Add from './components/Add'
import List from './components/List'
export default {
  name: '',
  components:{
    Header,
    Add,
    List
  },
  data(){
    return{
      comments:[
      {id:1,comment:'vue牛逼',username:'dd'},
      {id:2,comment:'vue牛逼',username:'yy'},
      {id:3,comment:'vue牛逼',username:'dyy'},
      {id:4,comment:'vue牛逼',username:'dd-yy'},
      ]
    }
  },
  methods: {
    // 添加一条评论
    addComment(comment){
      this.comments.unshift(comment)
    },
    addDelete(index){
      if(confirm('确认删除吗?')){
        this.comments.splice(index,1)
      }
        
    }
  },

}
</script>

<style scoped>

</style>
