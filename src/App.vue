<template>
  <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div>
  <h1>Vite+Vue</h1>
  <h2>{{ name }}今年{{ age }}岁了</h2>
  <h2>总冠军奖杯{{ number }}</h2>
  <h2>主修的学科为{{ study.sub }}</h2>
  <h2>一共有{{ study.sum }}种课程</h2>
  <button @click="changeStudy">课程数目+1</button>
  <button @click="changeNumber">总冠军数量+1</button>&nbsp;
  <button @click="changeAge">年龄+1</button>
  <hr>
  <Demo></Demo>
  <hr>
  <test></test>
  <hr>
</template>

<script>
import test from './components/test.vue'
import Demo from './components/Demo.vue'
import { reactive, ref, watch } from 'vue'
export default {
  name: 'App',
  components:{Demo,test},
  setup() {
    const name = 'Stephen Curry'
    const age = ref(20)
    const number = ref(0)
    const study = reactive({
      sub: 'english',
      sum: 5
    })
    // 在Vue3中使用 watch监视reactive控制的响应式数据会导致oldValue和newValue相同 ---小bug
    watch(study, (newValue, oldValue) => {
      console.log('study变化了', newValue, oldValue);
    })
     function changeNumber() {
      number.value++   
    }
    function changeAge() {
      age.value++
    }
    function changeStudy() {
      study.sum++
    }
    return {
      name,
      age,
      number,
      study,
      changeNumber,
      changeAge,
      changeStudy
    }
  }
}
</script>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>

