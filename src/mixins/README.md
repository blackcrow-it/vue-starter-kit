# Giới thiệu về mixin

## Cơ bản
Mixin là một cách linh hoạt để phân phối những tính năng tái sử dụng được cho component. Một object mixin có thể chứa bất kì những tùy chọn nào của component. Khi một component sử dụng một mixin, tất cả những tùy chọn trong mixin sẽ được “hòa trộn” (mixed) vào trong tùy chọn của component đó.
```js
// định nghĩa một object mixin
var myMixin = {
  created: function () {
    this.hello()
  },
  methods: {
    hello: function () {
      console.log('Mixin xin chào!')
    }
  }
}

// định nghĩa một component sử dụng mixin này
var Component = Vue.extend({
  mixins: [myMixin]
})

var component = new Component() // => "Mixin xin chào!"
```

## Hợp nhất các tùy chọn

Khi một mixin và component chứa những tùy chọn trùng nhau, những tùy chọn này sẽ được merge (hợp nhất) bằng cách sử dụng các chiến lược thích hợp.

Ví dụ, những object data sẽ được merge sâu một cấp (shallow merge), và khi có xung đột thì data của component sẽ được ưu tiên.

```js
var mixin = {
  data: function () {
    return {
      message: 'chào anh',
      foo: 'abc'
    }
  }
}

new Vue({
  mixins: [mixin],
  data: function () {
    return {
      message: 'chào chị',
      bar: 'def'
    }
  },
  created: function () {
    console.log(this.$data)
    // => { message: "chào chị", foo: "abc", bar: "def" }
  }
})
```
<a href="https://vi.vuejs.org/v2/guide/mixins.htm">Xem thêm</a>