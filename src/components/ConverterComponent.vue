<template>
    <div class="container">
        <h1>Конвертер миль в километры</h1>
        <h2>и обратно))</h2>
        <div class="input-group mb-3 text-center">
            <input type="number" class="form-control" placeholder="Мили" v-model="miles">
            <span class="input-group-text">⇄</span>
            <input type="number" class="form-control" placeholder="Километры" v-model="kilometers">
        </div>
    </div>
</template>

<script>
export default {
    name: "ConverterComponent",
    data() {
        return {
            kilometers: null,
            miles: null,
        }
    },
    watch: {
        kilometers: function(val) {
            this.kilometers = val;
            this.miles = this.kilometers / 1.609;
        },
        miles: function(val) {
            this.miles = val;
            this.kilometers = this.miles * 1.609;
        }
    }
}
</script>

<style>

</style>