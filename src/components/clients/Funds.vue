<template>
    <table class="table mb-4">
        <thead>
            <tr>
                <th>Класс акций</th>
                <th>Название фонда</th>
                <th>Управляющая компания</th>
                <th>Стоимость</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="value in funds.slice(0,10)" :key="value.funds">
                <td>{{value.symbol}}</td>
                <td>{{value.name}}</td>
                <td>{{value.exchange}}</td>
                <td>{{value.price}}</td>
            </tr>
        </tbody>
    </table>
</template>

<script lang="ts">
import axios from 'axios'

export default {
    name: 'Funds',
    data(){
        return{
            funds:[],
            errors:[],
        }
    },
    created(){
        axios.get('https://financialmodelingprep.com/api/v3/etf/list?apikey=6c2a639deeb85ca31e40915e5ebd107e')
            .then(responce =>{
                this.funds = responce.data
                console.log(responce)
            })
            .catch(e =>{
                this.errors.push(e)
            })
    }
}
</script>
<style scoped>
    table{
        @apply w-full;
    }
    th{
        @apply text-left px-2;

    }
    td{
        @apply px-2;
    }
    thead tr{
        @apply h-12  text-gray-500;
    }
    tbody tr{
        @apply bg-white h-12 border-b ;
    }
</style>

