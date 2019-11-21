<template>
    <div>
        <h1>Filters & Mixins</h1>
        <hr>
        <input v-model="filterText" />
        <ul>
            <li v-for="fruit in filteredFruits">{{ fruit }}</li>
        </ul>
    </div>
</template>

<script>
    import { friutMixin } from './friutMixin';
    export default {
        mixins: [friutMixin],
        created(){
            console.log('Inside List Create Hook');
        }
    }
</script>

<style>
</style>
