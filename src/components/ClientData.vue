<template>
    <form id="search">
        Search<input name="query" v-model="searchQuery"/>
    </form>
    <Demogrid
    :data = "gridData"
    :columns = "gridColumns"
    :filter-key = "searchQuery"
    />

</template>

<script setup>

import Demogrid from './Grid.vue'
import { ref } from 'vue'

const searchQuery = ref('')
const gridColumns = ['name', 'rank']
const gridData = [
    {name: 'Joe', rank: 6 },
    {name: 'Jill', rank: 9 },
    {name: 'Grace', rank: 0 },
    {name: 'Phin', rank: 6 },
]
</script>