<template>
    <div class="my-component">
        <!-- <div>{{ message }}</div>
        <div>{{ demo() }}</div>
        <div v-if="bien1">hiên</div>
        <div v-else>ẩn</div>
        <div><button @click="changeMessage">Click me</button></div> -->
        <ul>
            <li v-for="(value, key) in listNumber"  :key="key" >
                {{ key }} - {{ value }}
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                message: 'This is my first component using binding data',
                bien1: true,
                listNumber:[1,2,3,4,5,6,67,7,78,8,9]
            }
           
        },
        methods: {
            changeMessage() {
                this.bien1 = !this.bien1
            },
            demo() {
                console.log(this.bien1)
            }
        },
        watch: {
            bien1() {
                console.log('message changed')
            }
        }
    }
    
</script>

<style lang="scss" scoped>
    .my-component {
        color: red;
    }
</style>
