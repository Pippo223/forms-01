<template>
    <ul>
        <li :class="{active: modelValue === 'poor'}">
            <button type="button" @click="activate('poor')">Poor</button>
        </li>
        <li :class="{active: modelValue === 'average'}">
            <button type="button" @click="activate('average')">Average</button>
        </li>
        <li :class="{active: modelValue === 'great'}">
            <button type="button" @click="activate('great')">Great</button>
        </li>

    </ul>
</template>

<script>

export default {
    props:['modelValue'],
    emits: ['update:modelValue'],

    // data() {
    //     return {
    //         activeOption: null
    //     }
        
    // },

    // computed: {
    //     activeOption() {
    //         return this.modelValue;
    //     }
    // },

    methods: {
        activate(option) { 
           // this.activeOption = option;
            this.$emit('update:modelValue', option);
        }
    }
}
</script>


<style scoped>
    .active {
        border-color:magenta;
    }

    .active button{
        border-color:magenta;
    }

    ul {
        list-style: none;
        margin: 0.5rem 0;
        padding: 0;
        display: flex;
    }

    li {
        margin: 0 1rem;
        border: 1px solid #ccc;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    button {
        font: inherit;
        padding: 20px;
        border: 0;
        background-color: transparent;
        cursor: pointer;
    }
</style>