<template>
    <div>
        <p @click="add1" :style="{color:num>3?'red':'black'}">{{num}}</p>
        <span></span>
        <button @click="bigred"></button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            num: '0',
        }
    },
    methods: {
        add1() {
            this.num++;
            if (this, num > 3) {
                this.num.style
            }
        },
        bigred() {

        }
    }
}
</script>

<style>

</style>