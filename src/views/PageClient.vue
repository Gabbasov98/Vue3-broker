<template>
    <div>
       <div class="dashboard-info">
            <div class="dashboard-info__item">
                <div class="dashboard-info__icon">
                    <icon-deal />
                </div>
               <h3 class="dashboard-info__title"><span>Количество активов</span> 12</h3>
            </div>
            <div class="dashboard-info__item">
                <div class="dashboard-info__icon">
                    <icon-summ />
                </div>
               <h3 class="dashboard-info__title"><span>Сумма активов (RUB)</span> 3.700.000 ₽</h3>
            </div>
            <div class="dashboard-info__item">
                <div class="dashboard-info__icon">
                    <icon-summ />
                </div>
               <h3 class="dashboard-info__title"><span>Сумма активов (USD)</span> 100.000 $</h3>
            </div>
            <div class="dashboard-info__item">
                <div class="dashboard-info__icon">
                    <icon-activity />
                </div>
               <h3 class="dashboard-info__title"><span>Доход за сегодня</span> +25%</h3>
            </div>
       </div>
        <h3 class="title">Валюты</h3>
        <Currency />

        <h3 class="title">Криптоалюты</h3>
        <Crypto/>

        <h3 class="title">Акции</h3>
        <Stock/>

        <h3 class="title">Календарь девидендов</h3>
        <Funds/>

       <h3 class="title">Загрузка документов</h3>
       <formUpload/>
   </div>
</template>

<script lang="ts">
import IconSumm from "../components/icons/IconSumm.vue"
import IconActivity from "../components/icons/IconActivity.vue"
import IconDeal from "../components/icons/IconDeal.vue"
import formUpload from "../components/formUpload.vue"
import Currency from "../components/clients/Currency.vue"
import Crypto from "../components/clients/Crypto.vue"
import Stock from "../components/clients/Stock.vue"
import Funds from "../components/clients/Funds.vue"
    export default {
        name:"Admin",
        components:{IconDeal,IconActivity,IconSumm,formUpload,Currency,Crypto,Stock,Funds}
    }
</script>