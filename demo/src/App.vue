<template>
  <div>
    <input v-model="inputValue"/>
    <button @click="addList">提交</button>
  </div>
  <ul>
    <ListItem v-for="item of list" :key="item" :input-value="item"/>
  </ul>
</template>

<script>
import {ref, reactive} from 'vue'
import ListItem from '@/components/ListItem'

export default {
  name: 'App',
  components:{
    ListItem
  },
  setup(){
    const inputValue = ref('')
    const list = reactive([])
    const addList = () => {
      list.push(inputValue.value)
    }
    return {
      inputValue,
      list,
      addList
    }
  }

}
</script>

<style>
  ul {
    list-style: none;
  }
</style>
