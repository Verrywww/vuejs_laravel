<template>
    <div class="user-dashboard">
        <div class="list-user-comp">
            <ListUser @userSelected="childrenSelectUser"></ListUser>
        </div>
        <div class="user-detail-comp">
            <UserDetail :userDetailInfo="userSelectedFromChild"></UserDetail>
        </div>
    </div>
</template>

<script>
    import ListUser from './ListUser.vue'
    import UserDetail from './UserDetail.vue'
    export default {
        components: {
            ListUser,
            UserDetail
        },
        data() {
            return {
                userSelectedFromChild: {}
            }
        },
        methods: {
            // Process event emitted from child
            childrenSelectUser(user) {
                this.userSelectedFromChild = user
            }
        }
    }
</script>

<style lang="scss" scoped>
</style>