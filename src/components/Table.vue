<script setup lang="ts">
import { reactive, watch } from 'vue'
import Query from './Query.vue';
import QueryTable from './QueryTable.vue';

const queryData = reactive({
    name: 'saber'
})

watch(() => queryData.name, (newValues) => { console.log(newValues)})
</script>
<template>
 <div>
     <query>
         <template #item1>
             <el-input v-model="queryData.name"></el-input>
         </template>
     </query>
     <query-table>
         <template #table>
            <el-table-column prop="date" label="Date" width="180" />
            <el-table-column prop="name" label="Name" width="180" />
            <el-table-column prop="address" label="Address" />
         </template>
     </query-table>
 </div>
</template>