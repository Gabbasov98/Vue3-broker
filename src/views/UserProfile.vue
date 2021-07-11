<template>
    <div class="user-profile">
        <div class="user-profile-item user-profile-info" v-for="(table,index) in TableData.slice(0,1)" :key="index">
            <h2 class="user-profile__title">{{table.name}}</h2>
            <div class="user-profile__email">
                <span >{{table.email}}</span>
                <span :class="`px-3  text-xs leading-5 bg-${table.statusColor}-100 text-${table.statusColor}-700 inline-flex rounded-full`">{{table.status}}</span>
            </div>
        </div>
        <div class="user-profile-item user-profile-data">
            <div class="user-profile-data__blocks">
                <div class="user-profile-data__block">
                    <h3 class="title">Валюты</h3>
                    <Currency />
                </div>
                <div class="user-profile-data__block">
                    <h3 class="title">Криптоалюты</h3>
                    <Crypto/>
                </div>
            </div>
            <h3 class="title">Акции</h3>
            <Stock/>
        </div>
    </div>
    <div class="user" >
        
    </div>
    
</template>

<script lang="ts">
import { useTableData } from "../interfaces/useTableData"
import Currency from "../components/profile/Currency.vue"
import Crypto from "../components/profile/Crypto.vue"
import Stock from "../components/profile/Stock.vue"

export default {
    name:'UserProfile',
    components:{Currency,Crypto,Stock},
    setup() {
        const { TableData } = useTableData();
        return { TableData };
    }
}
</script>

<style scoped>
    .user{
        @apply flex justify-between
    }
    .user-profile-data__blocks{
        @apply flex justify-between
    }
    .user-profile-data__block{
        @apply w-6/12 mx-2
    }
</style>

