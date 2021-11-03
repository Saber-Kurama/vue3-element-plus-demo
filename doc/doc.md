vue3.0父组件调用子组件中的方法

```
<!-- 1. 在子组件上绑定ref -->
<children-component ref="getChildList"></children-component>
...
<script>
  import { ref } from 'vue'
  export default {
    setup () {
      // 2、父组件中定义和ref同名的变量
      const getChildList = ref(null)
      onMounted (() => {
        // 4、调用子组件中的getList()方法
        console.log(getChildList.value.getList())
      })
      return {
        // 3、return出去
        getChildList
      }
    }
  })

</script>

```

```
setup () {
  // 方法
  const getList = () => {
    console.log('子组件中的方法')
  }
  return {
    getList
  }
}
```
