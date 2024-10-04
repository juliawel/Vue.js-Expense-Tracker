<template>
  <Header/>
  <div class="container">
    <Balance :total="total"/>
    <IncomeExpenses/>
    <TransactionList transactions="transactions"/>
    <AddTransaction/>
  </div>
</template>

<script setup>  
  import Header from './components/Header.vue';
  import Balance from './components/Balance.vue';
  import IncomeExpenses from './components/IncomeExpenses.vue';
  import TransactionList from './components/TransactionList.vue';
  import AddTransaction from './components/AddTransaction.vue';

  import { ref, computed } from 'vue';

  const transactions = [

  ];

  const total =computed(() => {
    return transactions.value.reduce((acc, transaction) => {
      return acc + transaction.amount;
    }, 0)
  });

  /*
    // we do not need this when using 'setup' on <script>; '<script setup> ' 
    export default {
      components: {
      Header,
      Balance,
      IncomeExpenses,
      TransactionList,
      AddTransaction,
      }
  ''}*/
</script>