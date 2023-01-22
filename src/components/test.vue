<template>
    <h2>我是Test组件</h2>
    <h2>当前点击鼠标的位置是X:{{point.x}}-Y:{{point.y}}</h2>
</template>

<script>
import usePoint from '../hook/usehook'
export default {
    name:'Test',
    setup() {
        return usePoint()
    }
}
</script>
