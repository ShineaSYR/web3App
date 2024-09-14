<script setup>
// import { ref } from 'vue'
import { ref } from 'vue';
import Web3 from 'web3'

// 实例化web3
const web3 = new Web3(Web3.givenProvider || '')
console.log('web3', web3)

// 创建账号
// 只要执行一次，就创建一个新账号
// const account = web3.eth.accounts.create('123');
// console.log('account', account)
// console.log('account-address', account.address)
// console.log('account-privateKey', account.privateKey)


// // 创建账户信息
const address = ref('')
const privateKey = ref('')


// // 获取余额
const amount = ref(-1)
web3.eth.getBalance(address.value).then((res)=>{
    amount.value = res
    console.log('amount', amount.value)
})

// 单位转换
const num1 = web3.utils.toWei('0.3')
console.log('num1', num1)

</script>

<template>
  <!-- <h1>{{ msg }}</h1> -->
    <p>地址：{{ address }}</p>
    <p>地址：{{ privateKey }}</p>
    <p>地址：{{ mount }}</p>
  
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
