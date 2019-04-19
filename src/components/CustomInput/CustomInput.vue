<template>
    <!-- <div :class="$style.customInput">
        <div v-if="label" for="" :class="$style.label">{{label}}</div>
        <div v-if="validation" :class="$style.validation">!</div>
        <div :class="$style.input">
            <span v-if="icon" :class="$style.icon"></span>
            <input 
                :name="name" 
                type="text" 
                :placeholder="placeHolder"
                @input="onInput" 
                :value="value" 
                autocomplete="on">
        </div>
    </div> -->
    <div class="input-wrapper">
        <label 
            v-if="label" 
            for="name" 
            class="form-label" >{{label}}<span class="star-icon">*</span></label>
        <input 
            id="name" 
            class="form-input" 
            type="text" 
            :placeholder="placeHolder" 
            v-model="value" 
            maxlength="10" 
            @input="submitted">
        <img 
            v-if="hasIcon" 
            class="form-icon" 
            src="@/assets/icon/information-outline.svg" 
            alt=""> 
    </div>
</template>

<script>

export default {
    name: 'CustomInput',
    props: {
        label:{},
        placeHolder: {},
        hasIcon: {}
    },
    data () {
        return {  
            value : '',
        }
    },
    methods: {
        submitted() {
            this.$emit('input', this.value);
        }
    }
}
</script>

<style lang="scss">
    @import './customInput';
</style>

