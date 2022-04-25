# elt-transfer 概述
基于element-ui的可分页表格穿梭框. 本项目继承自github [elt-transfer](https://github.com/TanxiangCode/elt-transfer.git)，但在以下几方面做了修改：

1. 具名插槽 v-slot 支持vue2.6版本
2. 扩展穿梭框右侧 rightTableData 数据加载方法，可以异步进行加载
3. 支持数据重新加载
4. 增加穿梭框右侧可编辑
5. 穿梭框左侧选中状态支持异步渲染
6. 清理数据时，不再再次加载左侧 leftTableData 数据
7. 支持表单数据提交
8. 完善example代码



## 安装
`npm install elt-transfer`

## 使用
在main.js文件中引入插件并注册
``` js
import eltTransfer from 'elt-transfer'
Vue.use(eltTransfer)
```

## 示例

![截图](/examples/elt-transfer.jpeg)


[示例代码](/examples/App.vue)

## Attributes
| 参数 | 说明 | 类型 | 默认值 |
| :--- | :--- | :--- | :--- |
| value / v-model | 绑定值 | array | — |
| show-query | 是否需要显示条件查询 | boolean | false |
| show-pagination | 是否需要显示分页 | boolean | false |
| pagination-call-back | 分页回调，需要使用Promise返回结果 | function(pageIndex, pageSize) | { total: 0, data: null } |
| right-data-call-back | 回调，需要使用Promise返回结果 | function() | { data: null } |
| title-texts | 自定义标题文案 | array | ['待选项', '已选项'] |
| button-texts | 自定义按钮文案 | array | ['',''] |
| query-texts | 自定义查询按钮文案 | array | ['查询','筛选'] |
| left-columns | 左侧表格列定义, 需要属性{ id, label, width } | array | [] |
| right-columns | 右侧表格列定义, 不传时将使用left-columns的值  | array | undefined |
| min-height | 表格最小高度 | string | 300px |
| max-height | 表格最大高度 | string | 500px |
| table-row-key | 表格行数据的Key | function(row) | row.id |

## Methods
| 参数 | 说明 | 参数 |
| :--- | :--- | :--- |
| clear | 清除所有的操作后产生的数据 | - |
| etlTransferCreated | 重新加载数据 | - |

## Slot
| 名称 | 说明 |
| :--- | :--- |
| - | 自定义列的内容，参数为 { row, column } |
| lcondition | 左表查询条件插槽，可自行添加el-form-item，并绑定值至scope上，名称与字段名需相同 |
| rcondition | 同上 |


## RoadMap
1. 穿梭框左侧分页功能
2. leftTable、rightTable 可自适应宽度
3. 扩展部分接口 - 提交

