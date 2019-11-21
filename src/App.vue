<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <h1>Filters & Mixins</h1>
                {{ text | toUppercase | to-lowercase}}
                <hr>
                <button @click="fruits.push('Pumkins')">Add New Item</button>
                <input v-model="filterText" />
                <ul>
                    <li v-for="fruit in filteredFruits">{{ fruit }}</li>
                </ul>
                <hr>
                <app-list></app-list>
            </div>
        </div>
    </div>
</template>

<script>
    import List from './List.vue';
    import { friutMixin } from './friutMixin';

    export default {
        mixins: [friutMixin],
        data: function(){
            return{
                text: 'Hello There'
            }
        },
        components: {
            appList: List
        },
        filters: {
            toUppercase: function(value){
                return value.toUpperCase();
            },
            capitalize: function (value) {
                if (!value) return ''
                    value = value.toString()
                    return value.charAt(0).toUpperCase() + value.slice(1)
                }
        }
    }
</script>

<style>

</style>
