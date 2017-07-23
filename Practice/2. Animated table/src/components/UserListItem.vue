<template>
    <tr>
        <td>Jill</td>
        <td class="last-name">
            <div :style="collapseStyle">
                Smith
            </div>

        </td>
        <td>50</td>
    </tr>
</template>

<script>
    export default {
        name: 'UserListItem',
        props: {
            collapseStyle: Object
        }
    }
</script>

<style lang="scss" scoped>
    $time: 0.3s;
    td {
        border: 1px solid black;
        overflow: hidden;
        transition: opacity $time ease-out, width $time ease-out;
    }

    div {
        transition: opacity $time ease-out, width $time ease-out;
    }
</style>