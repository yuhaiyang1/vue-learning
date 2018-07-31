<template>
  <div id="example">
    <p>Original message: "{{ message }}"</p>
    <p>Computed reversed message: "{{ reversedMessage }}"</p>
    <span @click="lower($event, 11)">点击</span>
    <Watchs />
  </div>
</template>
<script>
import Watchs from './Watch.vue'
  export default {
    name: 'child1',
    components: {
     Watchs 
    },
    data (){
      return {message: 'abcdef'}
     },
    computed: {
      // 计算属性的 getter
      reversedMessage: function () {
        // `this` 指向 vm 实例
        return this.message.split('').reverse().join('')
      }
    },
    methods: {
      lower(e, data){
        console.log(e.target.innerHTML, data)
      }
    }
  }
</script>
