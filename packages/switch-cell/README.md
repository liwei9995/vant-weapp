# SwitchCell 开关单元格

### 引入
在`app.json`或`index.json`中引入组件，默认为`ES6`版本，`ES5`引入方式参见[快速上手](#/quickstart)

```json
"usingComponents": {
  "van-switch-cell": "path/to/vant-weapp/dist/switch-cell/index"
}
```

## 代码演示

### 基础用法

```html
<van-switch-cell
  title="标题"
  checked="{{ checked }}"
  bind:change="onChange"
/>
```

```javascript
Page({
  data: {
    checked: true
  },

  onChange(event) {
    // 需要手动对 checked 状态进行更新
    this.setData({ checked: event.detail });
  }
});
```

### 禁用状态
通过`disabled`属性可以将组件设置为禁用状态

```html
<van-switch-cell
  disabled
  title="标题"
  checked="{{ checked }}"
  bind:change="onChange"
/>
```

### 加载状态
通过`loading`属性可以将组件设置为加载状态

```html
<van-switch-cell
  loading
  title="标题"
  checked="{{ checked }}"
  bind:change="onChange"
/>
```

### Props

| 参数 | 说明 | 类型 | 默认值 |
|-----------|-----------|-----------|-------------|
| name | 在表单内提交时的标识符 | *string* | - |
| checked | 开关状态 | *any* | `false` |
| icon | 左侧图标名称或图片链接，可选值见 Icon 组件 | *string* | - |
| title | 左侧标题 |  *string* | `''` |
| label | 标题下方的描述信息 | *string* | - |
| loading | 是否为加载状态 |  *boolean* | `false` |
| disabled | 是否为禁用状态 |  *boolean* | `false` |
| size | 开关尺寸 | *string* | `24px` |
| active-color | 开关打开时的背景色 | *string* | `#1989fa` |
| inactive-color | 开关关闭时的背景色 | *string* | `#fff` |
| active-value | 打开时的值 | *any* | `true` |
| inactive-value | 关闭时的值 | *any* | `false` |
| use-label-slot | 是否使用 label slot | *boolean* | `false` |

### Events

| 事件名 | 说明 | 参数 |
|-----------|-----------|-----------|
| bind:change | 开关状态切换回调 | event.detail: 是否选中开关 |

### Slot

| 名称 | 说明 |
|-----------|-----------|
| title | 自定义`title`显示内容，如果设置了`title`属性则不生效 |
| label | 自定义`label`显示内容，需要设置 `use-label-slot`属性 |
| icon | 自定义`icon`显示内容，如果设置了`icon`属性则不生效 |
