<template>
    <div class="container">
        <h1>{{ name }}</h1>
        <div class="input-group mb-3 text-center">
            <input type="text" class="form-control" placeholder="Мили" v-model="sourceValue">
            <span class="input-group-text">→</span>
            <input type="text" class="form-control" placeholder="Километры" :value="convertMilesToKm">
        </div>
    </div>
</template>

<script>
export default {
    name: "ConverterComponent",
    props: {
        name: String,
    },
    data() {
        return {
            sourceValue: null,
        }
    },
    computed: {
        convertMilesToKm() {
            if (this.sourceValue == null || isNaN(this.sourceValue)) {
                return;
            } else {
                return this.sourceValue * 1.609;
            }
        }
    }
}
</script>

<style>

</style>