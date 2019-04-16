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
        <label class="form-label" for="">این تست است</label>
        <input class="form-input" type="text" placeholder="این تست هست">
        <img src="/src/assets/icon/information-outline.svg" alt="">
    </div>
</template>

<script>

export default {
    name: 'CustomInput',
    data () {
        return {  

        }
    }
}
</script>

<style lang="scss">
    @import './custom-input';
</style>

