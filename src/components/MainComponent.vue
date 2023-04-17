<template>
    <div class="row">
        <CardComponent v-for="(card,index) in store.cardList" :key="card.id" />
    </div>
</template>

<script>
import { store } from '../../data/store';
import CardComponent from '../components/CardComponent.vue'
    export default {
        name: 'MainComponent',
        components:{
            CardComponent
        },
        data(){
            return{
                store
            }
        }
    }
</script>

<style lang="scss" scoped>
@use '../assets/partials/variables' as *;
body{
    background-color: $my-bg;
}
</style>