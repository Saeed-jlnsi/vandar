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
    <div class="text-area-wrapper">
        <label v-if="label" for="text-area" class="form-label" >{{label}}<span class="star-icon">*</span></label>
        <textarea name="text-area" id="text-area" class="form-text-area"></textarea>
    </div>
</template>

<script>

export default {
    name: 'CustomTextArea',
    props: {
        label:{},
    },
    data () {
        return {  

        }
    }
}
</script>

<style lang="scss">
    @import './custom-text-area';
</style>

