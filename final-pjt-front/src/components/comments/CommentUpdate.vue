<template>
<div>
  <div v-if="commentcheck">
    {{comment.id}}
    수정 내용: <input @keypress.enter="updateComment(comment)" type="text" v-model.trim="comment.context">
    <button @click="updateComment(comment)">제출</button>
    <p></p>
  </div>
  </div>

  
</template>

<script>
import { mapActions, mapState } from 'vuex'
export default {
  name: 'CommentUpdate',
  props: {
    comment: Object
  },
  // data: function () {
  //   return {
  //       comment: {
  //         context:''
  //       },
  //     }
  // },
  computed: {
    ...mapState([
      'commentcheck',

    ])
  },
  methods:{
    ...mapActions([
      'updateComment'
    ])
  
  }
}
</script>

<style scoped>
  :root {
  background: #f5f6fa;
  color: #9c9c9c;
  font: 1rem "PT Sans", sans-serif;
}

html,
body,
.container {
  height: 100%;
}

a {
  color: inherit;
}
a:hover {
  color: #7f8ff4;
}

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.uppercase {
  text-transform: uppercase;
}

.btn {
  display: inline-block;
  background: transparent;
  color: inherit;
  font: inherit;
  border: 0;
  outline: 0;
  padding: 0;
  transition: all 200ms ease-in;
  cursor: pointer;
}
.btn--primary {
  background: #7f8ff4;
  color: #fff;
  box-shadow: 0 0 10px 2px rgba(0, 0, 0, 0.1);
  border-radius: 2px;
  padding: 12px 36px;
}
.btn--primary:hover {
  background: #6c7ff2;
}
.btn--primary:active {
  background: #7f8ff4;
  box-shadow: inset 0 0 10px 2px rgba(0, 0, 0, 0.2);
}
.btn--inside {
  margin-left: -96px;
}

.form__field {
  width: 360px;
  background: #fff;
  color: #a3a3a3;
  font: inherit;
  box-shadow: 0 6px 10px 0 rgba(0, 0, 0, 0.1);
  border: 0;
  outline: 0;
  padding: 22px 18px;
}
</style>