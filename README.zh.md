# BeeGridTable [(English)](./README.md)

#### 描述

BeeGridTable ，是一款基于 Vue2.js 的可高定制化的表格控件. 更丰富的功能、更加高效、易于使用!

#### [主页](http://www.beegridtable.com/index)

http://www.beegridtable.com/index

#### 安装

-   1.  npm

```
npm i beegridtable -S
```

-   2.  Or yarn

```
yarn add beegridtable
```

#### 功能

-   Friendly API.
-   Great documentation.
-   It is awesome.
-   Support Vue.js 2.

#### 如何使用

-   首先, 引入 BeeGridTable
    一般在 webpack 入口页面 main.js 中如下配置:

```
import Vue from "vue";
import App from "./App.vue";
import router from "./router";
import store from "./store";

import BeeGridTable from "beegridtable";
import BeeLocale from "beegridtable/src/locale";

Vue.use(BeeGridTable, {
  BeeLocale,
  capture: true,
});

Vue.config.productionTip = false;

new Vue({
  router,
  store,
  render: (h) => h(App),
}).$mount("#app");
```

-   最简单的例子

![basic.png](./demos/basic.png)

```
//Vue Template
<BeeGridTable
    :columns="columns"
    :data="data"
></BeeGridTable>

// JS
data() {
    return {
      columns: [
        {
          title: "Name",
          key: "name",
          align: "center",
          resizable: true,
        },
        {
          title: "Age",
          key: "age",
          align: "center",
          sortable: true,
        },
        {
          title: "Street",
          key: "street",
          align: "center",
          resizable: true,
        },
        {
          title: "Gender",
          key: "gender",
          align: "center",
        },
      ],
      data: [],
    };
  },
```

-   固定表项功能
    ![fixed.png](./demos/fixed.png)

```
//Vue Template
<BeeGridTable
    border
    height="560"
    :showSummary="false"
    :columns="columns"
    :data="data"
>
    <template slot-scope="{ column }" slot="hop">
    <Button type="primary" size="small" style="margin-right: 5px"
        >刷新</Button
    >
    <Button type="warning" size="small" @click="addPatient(column)"
        >新增</Button
    >
    </template>
    <template slot-scope="{ row, index }" slot="op">
    <Button type="warning" size="small" style="margin-right: 5px"
        >编辑</Button
    >
    <Button type="error" size="small" @click="handleDelete(row, index)"
        >删除</Button
    >
    </template>
</BeeGridTable>

//JS
columns: [
    {
        title: "排队编号",
        key: "dialysisNumber",
        fixed: "left",
        width: 150,
        filterHeight: 50,
        resizable: true,
    },
    {
        title: "姓名",
        key: "name",
        fixed: "left",
        width: 150,
        filterHeight: 50,
        resizable: true,
    },
    { title: "性别", key: "sexName", width: 150, resizable: true },
    { title: "年龄", key: "birthDay", width: 150, resizable: true },
    {
        title: "排队分组",
        key: "doctorGroupName",
        width: 150,
        resizable: true,
    },
    {
        title: "状态",
        key: "treatStatusName",
        width: 150,
        resizable: true,
    },
    { title: "描述", key: "diagnosis", width: 150, resizable: true },
    { title: "血管路", key: "bloodRoad", resizable: true },
    { title: "队伍", key: "schedules", width: 150, resizable: true },
    { title: "严重程度", key: "visitTypeName", width: 150, resizable: true },
    { title: "诊疗", key: "termTypeName", width: 150, resizable: true },
    {
        title: "首次冒险",
        key: "firstTreatDate",
        width: 150,
        resizable: true,
    },
    { title: "手机号码", key: "peopleCode", width: 150, resizable: true },
    { title: "证件号", key: "idNumber", width: 150, resizable: true },
    {
        title: "操作",
        slot: "op",
        headSlot: "hop",
        fixed: "right",
        canEdit: false,
        key: "op",
        hideFilter: true,
        resizable: true,
        //   filterHeight: 50,
        width: 150,
    },
    ],
```

#### [More](http://www.beegridtable.com/index)

#### [License MIT](./LICENSE)