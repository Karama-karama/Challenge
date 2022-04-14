<script setup>
import { ref } from 'vue';
import { MDCDataTable } from '@material/data-table';

defineProps({
  msg: String,
  alert: String,
});
//Declaring const here
const columns = [
  {
    title: 'Name',
    dataIndex: 'name',
    key: 'name',
    fixed: true,
  },
  {
    title: 'Age',
    dataIndex: 'age',
    key: 'age',
  },
  {
    title: 'Address',
    dataIndex: 'address',
    key: 'address',
  },
  {
    title: 'Action',
    key: 'action',
  },
];
const data = [
  {
    key: 1,
    name: 'John Brown',
    age: 32,
    address: 'New York No. 1 Lake Park',
    description:
      'My name is John Brown, I am 32 years old, living in New York No. 1 Lake Park.',
  },
  {
    key: 2,
    name: 'Jim Green',
    age: 42,
    address: 'London No. 1 Lake Park',
    description:
      'My name is Jim Green, I am 42 years old, living in London No. 1 Lake Park.',
  },
  {
    key: 3,
    name: 'Joe Black',
    age: 32,
    address: 'Sidney No. 1 Lake Park',
    description:
      'My name is Joe Black, I am 32 years old, living in Sidney No. 1 Lake Park.',
  },
];
</script>

<template>
  <h1>{{ msg }}</h1>
  <h5>{{ alert }}</h5>
  <a-space align="center" style="margin-bottom: 16px">
    CheckStrictly:
    <a-switch v-model:checked="rowSelection.checkStrictly"></a-switch>
  </a-space>
  <a-table
    :columns="columns"
    :data-source="data"
    :row-selection="rowSelection"
  />
</template>
<script>
import { defineComponent } from 'vue';
export default defineComponent({
  setup() {
    return {
      data,
      columns,
    };
  },
});
</script>

<style scoped>
a {
  color: #42b983;
}
</style>
