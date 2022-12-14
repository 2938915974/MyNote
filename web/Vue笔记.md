# Vue 笔记

[TOC]

## v-for(待完善)

### `v-for="item in items" :key="item.message"`

  我们可以用 v-for 指令基于一个数组来渲染一个列表。v-for 指令需要使用 item in items 形式的特殊语法，其中 items 是源数据数组，而 item 则是被迭代的数组元素的别名。

```html
<ul id="example-1">
    <li v-for="item in items" :key="item.message">
        {{ item.message }}
    </li>
</ul>
```

还有 js 代码：

```js
var example1 = new Vue({
        el: '#example-1',
        data: {
            items: [
                { message: 'Foo' },
                { message: 'Bar' }
            ]
        }
    })
```

结果：

```htnl
Foo
Bar
```

### v-for="(item, index) in items

在 v-for 块中，我们可以访问所有父作用域的 property。v-for 还支持一个可选的第二个参数，即当前项的索引。

```html
<ul id="example-2">
    <li v-for="(item, index) in items">
        {{ parentMessage }} - {{ index }} - {{ item.message }}
    </li>
</ul>
```

与 js 代码 ：

```js
    var example2 = new Vue({
        el: '#example-2',
        data: {
            parentMessage: 'Parent',
            items: [
                { message: 'Foo' },
                { message: 'Bar' }
            ]
        }
    })
```

结果：
