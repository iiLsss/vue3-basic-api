## 1. ref

接受一个参数值并返回一个响应式且可改变的 ref 对象
  - ref 对象拥有一个指向内部值的单一属性 .value
  - 当ref在模板中使用的时候，它会自动解套，无需在模板内额外书写 .value

```html
<button @click="add">+</button>
<button @click="reduce">-</button>
{{count}}
```

```js
import { ref } from 'vue'
export default {
  setup () {
    const count = ref(0)
    console.log(count)
    const reduce = () => {
      count.value--
    }
    const add = () => {
      count.value++
    }
    return {
      reduce,
      add,
      count
    }
  }
}
```

## 2. unref

