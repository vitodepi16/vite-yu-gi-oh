<template>
    <div>
    <div class="row">
        <div class="card text-center">
            <div class="card-head">
               
            </div>
            <div class="card-body">
                <h4>{{ card }}</h4>
            <div>{{ card }}</div>
            </div>
            
        </div>
    </div>
</div>
</template>

<script>
    export default {
        name:'CardComponent',
        props: ['card'],
    }
</script>

<style lang="scss" scoped>

</style>