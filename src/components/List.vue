<template>
  <div class="list">
    <div clas="listheader">
      <p class="list-title">{{ title }}</p>
      <div class="deletelist" @click="removeList">X</div>
    </div>
  </div>
</template>

<script>
  export default {
    props: {
    title: {
      type:String,
      required:true
      },
      listindex: {
        type: Number,
        required: true
      }
    },
    methods: {
      removeList:function() {
        if(confirm('本当にこのリストを削除しますか？')){
          this.$store.dispatch('removelist',{listindex:this.listindex})
        }
      },
    }
  }
</script>