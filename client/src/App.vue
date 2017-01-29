<template>
    <div id="app">
        <img src="./assets/logo.png">
        <hello></hello>
        <user-list :userList="userList"></user-list>
    </div>
</template>

<script>
    import userServices from './services/userServices';
    import Hello from './components/Hello';
    import UserList from './components/user/UserList';

    export default {
        name: 'app',
        data() {
            return {
                userList: [],
            };
        },
        created() {
            userServices.getUsers()
                .then((users) => {
                    this.userList = users;
                });
        },
        components: {
            Hello,
            UserList,
        },
    };
</script>

<style>
    $test: #DDDDDD;
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
        background: $test;
    }
</style>
