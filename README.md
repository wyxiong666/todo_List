
# 基于vue2.0+vuex+localStorage写的记事本

## 写在前面

> 这个demo虽然功能少，但是其知识点很精华 基本上vuex知识点大部分都在这里面了。



## 代码预览

> vuex官方文档 https://vuex.vuejs.org/ 我觉的官方文档说明很详细<br>

> localStorage用来本地储存

```bash
const state={
    home:localStorage["home"]?JSON.parse(localStorage["home"]): [],
    item:localStorage["item"]?JSON.parse(localStorage["item"]): [],
}

export default state

```

```bash
const mutations={

    [types.SET_SHIXIANG](state,data){
        state.home.push(data)
        localStorage.setItem("home",JSON.stringify(state.home));
    },

    [types.SET_YES](state,data){
        state.item.push(data)
        localStorage.setItem("item",JSON.stringify(state.item));
    }
}

export default mutations

```


```bash
const actions={
    setOrder ({commit}, data) {
        commit('SET_SHIXIANG', data);
    },
    setYes({commit},data){
        commit('SET_YES',data)
    }
}

export default actions

```

## 项目启动

``` bash
# 安装依赖
npm install

# 打开端口号8080（默认）
npm run dev

# 启后台
npm run build
```
