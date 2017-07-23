<template>
    <div>
        <table class="user-list" :style="widthStyle">
            <tr>
                <th class="first-name">Firstname</th>
                <th class="last-name" :style="collapseStyle">Lastname</th>
                <th class="age" >Age</th>
            </tr>
            <UserListItem :collapseStyle="collapseStyle" v-for="n in 10" :key="n"></UserListItem>
        </table>
        <button @click="collapse">click</button>
        </div>
</template>

<script>
    import UserListItem from './UserListItem.vue';

    export default {
        name: 'userList',
        components: {
            UserListItem
        },
        data() {
            return {
                tWidth: 100,
                collapseWidth: 30,
                tOpacity: 1
            }
        },
        computed: {
            widthStyle() {
                return {
                    width: `${this.tWidth}%`
                }
            },
            collapseStyle() {
                return {
                    opacity: `${this.tOpacity}`,
                    width: `${this.collapseWidth}%`,
                }
            }
        },
        methods: {
            collapse() {
                this.tWidth === 30 ? this.tWidth = 100: this.tWidth = 30;
                this.collapseWidth === 30? this.collapseWidth = 0 : this.collapseWidth = 30;
                this.tOpacity === 1? this.tOpacity = 0 : this.tOpacity = 1;
            }
        }
    }
</script>

<style lang="scss" scoped>
    $time: 0.3s;

    table {
        table-layout: fixed;
        overflow: hidden;
    }

    .user-list {
        transition: width $time ease-out;
    }

    .last-name {
        transition: opacity $time ease-out, width $time ease-out;
    }

</style>