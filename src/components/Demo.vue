<template>
  <div>
    <h2>这是Demo组件</h2>
    <h2>当前点击鼠标的位置是X:{{point.x}}-Y:{{point.y}}</h2>
  </div>
</template>

<script>
import usePoint from '../hook/usehook';
export default {
    name:'Demo',
    setup(){
        return usePoint()
    },
}
</script>

<style>

</style>