<template>
  <div id="app">
    <UserList></UserList>
  </div>
</template>

<script>
    import UserList from './components/UserList.vue';

    export default {
        name: 'app',
        components: {
            UserList
        },
        data () {
            return {
            }
        }
    }
</script>

<style lang="scss" scoped>
  #app {
    width: 80%;
    margin: auto;
  }
</style>
