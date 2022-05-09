<template lang="">
    <div>
        <ul >
            <li v-for="(listItem, i) in listItems" :key="i">
                <span>{{listItem}}</span>
                <button @click="deleteListItem(i)">Eliminar</button>
            </li>
        </ul>
        <button @click="deleteList">Borrar todo</button>

    </div>
</template>
<script>
    export default {
        props: {
            listItems: {
                type: Array,
                required: true
            }
        },
        data() {
            return {

            }
        },
        methods: {
            deleteListItem(index){
                this.$emit('delete-item', index);
            },
            deleteList(){
                this.$emit('delete-list')
            }
        },
    }
</script>
<style lang="">

</style>