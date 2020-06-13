# Phần thư mục store là kho chứa biến trung tâm nhưng chỉ là biến của view (khuyến khích sử dụng Vuex)

## File index.js
Khai báo các biến state, các hàm xử lý, ... hoặc có thể để gộp các modules

## Folder modules
Thư mục này dùng để chia nhỏ file index.js, các file trong thư mục này tương tự như file index.js

## Ví dụ
index.js
```js
import Vue from 'vue'
import Vuex from 'vuex'

Vue.use(Vuex)

const store = new Vuex.Store({
  state: {
    count: 0
  },
  mutations: {
    increment (state) {
      state.count++
    }
  }
})
```
```js
store.commit('increment')

console.log(store.state.count)
```