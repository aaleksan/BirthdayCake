<template>
    <li>
        <div class="profilePic inline">
            <img :src="user.profilePic" alt="profile picture">
        </div>
        <div class="inline">
            {{ user.firstName }} {{ user.lastName }}
        </div>
        <div class="inline">
            button area
        </div>
    </li>
</template>

<script>
    export default {
        props: ['user'],
    };
</script>

<style scoped>
    li {
        background: #ccc;
        margin: 5px 0 5px 0;
        border-radius: 5px;
    }
    .inline {
        display: inline-block;
    }
</style>