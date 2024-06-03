# Class & Style 绑定

一个常见的需求是操作元素的`class`列表和内联样式。因为这些都是`attribute`，所以我们可以使用`v-bind`来处理。

## 绑定 HTML Class

### 对象语法：
我们可以传给`vbind:class`一个对象来动态切换`class`， 比如

```html
<div v-bind:class="{ active: isActive }"></div>
```

这里`active`存在与否取决于`isActive`的结果是true or false。 当然我们也可以向对象中传入更多的字段来切换多个`class`，并且`v-bind`也可以和普通`class`共存
当我们有

```html
<div class="static" v-bind:class="{ active: isActive, 'text-danger':hasError"><div>
```


以及 data 如下

```js
data: {
    isActive: true,
    hasError: false
}
```
， 我们的结果会被渲染为

```html
<div class="static active"></div>
```

并且当`isActive`或者`hasError`发生变化时，class列表会随之更新。

绑定数组的对象也不一定需要被定义在模板内

```js
data: {
    classObject: {
        active: true,
        'text-danger': false
    }
}
```

```html
<div v-bind:class="classObject"></div>
```

并且在这里我们可以使用 `computed` 计算属性来帮忙

```js
data: {
    isActive: true,
    error: null
},
computed: {
    classObject: function () {
        return {
        active: this.isActive && !this.error,
        'text-danger': this.error && this.error.type === 'fatal'
        }
    }
}
```

### 数组语法:

我们可以把一个数组传给 `v-bind:class`，以应用一个 `class` 列表：

```html
<div v-bind:class="[activeClass, errorClass]"></div>
```

```js
data: {
  activeClass: 'active',
  errorClass: 'text-danger'
}
```

渲染为：

```html
<div class="active text-danger"></div>
```

如果你也想根据条件切换列表中的 `class`，可以用三元表达式：

```html
<div v-bind:class="[isActive ? activeClass : '', errorClass]"></div>
```

这样写将始终添加 `errorClass`，但是只有在 `isActive` 是 true 时才添加 `activeClass`

不过，当有多个条件 `class` 时这样写有些繁琐。所以在数组语法中也可以使用对象语法：

```html
<div v-bind:class="[{ active: isActive }, errorClass]"></div>
```

### 组件样式

当在一个自定义组件上使用 `class` property 时，这些 `class` 将被添加到该组件的根元素上面。这个元素上已经存在的 `class` 不会被覆盖。

例如，如果你声明了这个组件：

```js
Vue.component('my-component', {
  template: '<p class="foo bar">Hi</p>'
})
```

然后在使用它的时候添加一些 `class`

```html
<my-component class="baz boo"></my-component>
```

HTML 将被渲染为：

```html
<p class="foo bar baz boo">Hi</p>
```

对于带数据绑定 `class` 也同样适用：

```html
<my-component v-bind:class="{ active: isActive }"></my-component>
```

当 `isActive` 为 true 时，HTML 将被渲染成为：

```html
<p class="foo bar active">Hi</p>
```

# 绑定内联样式

## 对象语法

`v-bind:style` 的对象语法十分直观——看着非常像 CSS，但其实是一个 JavaScript 对象。CSS property 名可以用驼峰式 (camelCase) 或短横线分隔 (kebab-case，记得用引号括起来) 来命名：

```html
<div v-bind:style="{ color: activeColor, fontSize: fontSize + 'px' }"></div>
```

```js
data: {
  activeColor: 'red',
  fontSize: 30
}
```

直接绑定到一个样式对象通常更好，这会让模板更清晰：

```html
<div v-bind:style="styleObject"></div>
```

```js
data: {
  styleObject: {
    color: 'red',
    fontSize: '13px'
  }
}
```

同样的，对象语法常常结合返回对象的计算属性使用。

## 数组语法

`v-bind:style` 的数组语法可以将多个样式对象应用到同一个元素上：

```html
<div v-bind:style="[baseStyles, overridingStyles]"></div>
```

**v-bind 缩写**:
```html
    <!-- 完整语法 -->
    <a v-bind:href="url">...</a>

    <!-- 缩写 -->
    <a :href="url">...</a>

    <!-- 动态参数的缩写 (2.6.0+) -->
    <a :[key]="url"> ... </a>
```


