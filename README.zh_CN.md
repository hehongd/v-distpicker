
# V - Distpicker



 

[English](./README.md) | [简体中文]

 
### 文档 

[文档 和 Demo ](https://jcc.github.io/v-distpicker/)

[更新日志](./CHANGELOG.zh-CN.md)

 
### 使用

#### Vue 2  安装1.x 版本

```shell
 npm install v-distpicker@^1.3.1 --save
```

```vue
<template>

<v-distpicker :province="select.province" :city="select.city" :area="select.area" @selected="onSelect" @province="selectProvince" @city="selectCity" @area="selectArea"></v-distpicker>

</template>


<script>

import VDistpicker from 'v-distpicker'
export default {
  components: { VDistpicker },
  data(){
    return {
       select:{ province: '', city: '', area: ''}
    }
  },
  methods:{
    onSelect(data) {
         console.log(data)
    },
    selectProvince({code,value}) {
        this.select.province = value
        console.log({code, value})
    },
    selectCity({code,value}) {
        this.select.city = value
        console.log({code, value})
    },
    selectArea({ code, value }) {
        this.select.area = value
        console.log({code, value})
    }
  }
}
</script>
```


#### Vue 3  安装2.x 版本

```shell
 npm install v-distpicker@^2.0.8 --save
```

```vue
<template>

<v-distpicker :province="select.province" :city="select.city" :area="select.area" @selected="onSelect" @change="onChange" @province="selectProvince" @city="selectCity" @area="selectArea"></v-distpicker>

</template>

<script setup>

import VDistpicker from 'v-distpicker'
let select = reactive({ province: '', city: '', area: '' })
function onSelect(data) {
  console.log(data)
}
function onChange(data){
   console.log(data)
}
function selectProvince({code,value}) {
  select.province = value
  console.log({code, value})
}
function selectCity({code,value}) {
  select.city = value
  console.log({code, value})
}
function selectArea({ code, value }) {
  select.area = value
  console.log({code, value})
}
</script>
```


## 版本发布

```shell
1.更新 package.json 和 package-lock.json中的 version
2.npm run build
3.git tag v2.0.x
4.git push origin :refs/tags/v2.0.x
```




## 数据来源

* 国家统计局：[统计用区划代码和城乡划分代码](http://www.stats.gov.cn/tjsj/tjbz/tjyqhdmhcxhfdm/2021/index.html) 数据一年一更
* 国家民政部：[中华人民共和国行政区划代码](http://www.mca.gov.cn/article/sj/tjbz/a/)  数据一月一更


## 贡献代码

Vue 2 --->> 提交到  0.1 分支

Vue 3 --->> 提交到  master 分支


 *   如何更新文档？ 

`npm run build:example`,并同步到 gh-pages分支












### 问题

*   省市区数据缺失了怎么办 ？

1.校验数据源中是否存在。
  
2.可以通过props 自定义数据源 

3.确实缺少的，欢迎 fork 和 PR 

<br>



