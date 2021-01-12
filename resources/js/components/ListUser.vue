<template>
    <div v-on:click="getUser" class="list-user">
        This is List user
        <ul>
            <li v-for="(item,key) in listUser" :key="key"><td><a @click="selectUser(item)">{{ item.name}}</a></td></li>
        </ul>
    </div>
</template>

<script>
    export default {
        data(){
            return{
                listUser:[],
            }
           
        },
         methods: {
                getUser(){
                    axios.get('https://5ff6b33ae7164b0017e19993.mockapi.io/user')
                    .then(response => {
                        console.log(this)
                        this.listUser = response.data
                    })
                    .catch(function (error) {
                        // handle error
                        console.log(error);
                    })
                },
                 selectUser(user) {
                        this.$emit('userSelected', user)
                    }
            }

    }
    console.log(this)
    
</script>

<style lang="scss" scoped>
</style>