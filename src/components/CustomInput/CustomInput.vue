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
        <label for="name" class="form-label" >نام انگلیسی برند<span class="star-icon">*</span></label>
        <input id="name" class="form-input" type="text" placeholder="این تست هست">
        <img class="form-icon" src="/src/assets/icon/information-outline.svg" alt=""> 
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

