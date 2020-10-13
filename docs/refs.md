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

如果参数是ref对象，则返回`.value`，否则原样返回

```js
const count = ref(0)
const num = 12
console.log(count) // RefImpl {_rawValue: 0, _shallow: false, __v_isRef: true, _value: 0}
console.log(unref(count)) // 0
console.log(unref(num)) // 12
```

## 3. toRef

用于响应式对象上的属性的引用。保持引用的响应
可用于为源反应对象上的属性创建引用。然后可以传递参考，从而保持与其源属性的反应性连接

```js
const state = reactive({count: 1, name: 'diqiu'})
const countRef = toRef(state, 'count')

const count = state.count
state.count = 10000

console.log(state) // Proxy {count: "10000", name: "diqiu"}
console.log(count) // 1
console.log(countRef.value) // 10000
```

## 4. toRefs

将反应对象转换为普通对象，其中所得对象的每个属性都是指向原始对象相应属性的ref。

```js

```

## 5. customRef

检查值是否是引用对象

```js

```