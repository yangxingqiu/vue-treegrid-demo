<template>
  <div id="app">
    <tree
      :data="data"
      :props="defaultProps"
      node-key="id"
      show-checkbox
      default-expand-all
      :expand-on-click-node="false"
      :columns="columns"
      ref="tree1"
      >
    </tree>
  </div>
</template>

<script>
import tree from '../../treegrid/dist/'
console.log(tree)
export default {
  name: 'app',
  data () {
    return {
      columns: [{
        minWidth: 300,
        label: '名称',
        name: 'name'
      }, {
        minWidth: 100,
        label: '编码',
        name: 'code'
      }, {
        minWidth: 300,
        label: '描述',
        name: 'txtDesc'
      }, {
        minWidth: 100,
        label: '类型',
        name: 'dropType'
      }, {
        width: 240,
        minWidth: 240,
        label: '操作',
        renderContent: this.renderContent
      }],
      data: [{
        id: 1,
        name: '一级 1',
        code: 123,
        txtDesc: '123',
        dropType: '123',
        children: [{
          id: 4,
          name: '二级 1-1',
          code: 123,
          txtDesc: '123',
          dropType: '123',
          children: [{
            id: 9,
            name: '三级 1-1-1',
            code: 123,
            txtDesc: '123',
            dropType: '123'
          }, {
            id: 10,
            name: '三级 1-1-2',
            code: 123,
            txtDesc: '123',
            dropType: '123'
          }]
        }]
      }, {
        id: 2,
        name: '一级 2',
        code: 123,
        txtDesc: '123',
        dropType: '123',
        children: [{
          id: 5,
          name: '二级 2-1',
          code: 123,
          txtDesc: '123',
          dropType: '123'
        }, {
          id: 6,
          name: '二级 2-2',
          code: 123,
          txtDesc: '123',
          dropType: '123'
        }]
      }, {
        id: 3,
        name: '一级 3',
        code: 123,
        txtDesc: '123',
        dropType: '123',
        children: [{
          id: 7,
          name: '二级 3-1',
          code: 123,
          txtDesc: '123',
          dropType: '123'
        }, {
          id: 8,
          name: '二级 3-2',
          code: 123,
          txtDesc: '123',
          dropType: '123'
        }]
      }],
      defaultProps: {
        children: 'children',
        label: 'label'
      }
    }
  },
  components: {
    tree
  }
}
</script>

<style>

</style>
