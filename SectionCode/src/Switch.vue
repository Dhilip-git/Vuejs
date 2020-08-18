<template>
    <div>
    <p>{{ `MR ${first} ${second}` }}</p>
        <button
                id="on"
                v-if="value"
                @click="switched(value)"
                :class="{active: value}">On</button>
        <button
        v-else
                id="off"
                @click="switched(value)"
                :class="{active: !value}">Off</button>
                 <p>test{{ value ? "true" : "false" }}</p>
    </div>
</template>

<script>
    export default {
        props:['value','first','second', 'update'],
        methods:{
           switched(test){
        this.update(!test)
           }

        }
    }
</script>

<style scoped>
    #on, #off {
        width: 40px;
        height: 20px;
        background-color: lightgray;
        padding: 2px;
        display: inline-block;
        margin: 10px -2px;
        box-sizing: content-box;
        cursor: pointer;
        text-align: center;
    }

    #on:hover, #on.active {
        background-color: lightgreen;
    }

    #off:hover, #off.active {
        background-color: lightcoral;
    }
</style>