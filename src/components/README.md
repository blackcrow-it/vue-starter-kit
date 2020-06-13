# Đây là ví dụ về một component trong Vue:
```js
// Định nghĩa một component với tên là "button-counter"
Vue.component('button-counter', {
  data: function () {
    return {
      count: 0
    }
  },
  template: '<button v-on:click="count++">Bạn đã bấm {{ count }} lần.</button>'
})
```
### Component là các đối tượng Vue có thể sử dụng lại được với một cái tên: trong trường hợp này là <code style="color: #e96900; background-color: #F8F8F8; "> button-counter</code>. Chúng ta có thể dùng component này như là một phần tử bên trong đối tượng Vue gốc được tạo bởi <code style="color: #e96900; background-color: #F8F8F8; ">new Vue</code>:
```html
<div id="components-demo">
  <button-counter></button-counter>
</div>
```
```js
new Vue({ el: '#components-demo' })
```
<a href="https://vi.vuejs.org/v2/guide/components.html">Xem thêm</a>