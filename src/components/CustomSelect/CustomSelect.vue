<template>
    <div class="select-wrapper">
        <label 
            v-if="label" 
            class="form-label" 
            for="">{{label}}<span class="star-icon">*</span></label>
        <select class="form-select">
            <option value="0">تهران</option>
            <option value="1">لاهیجان</option>
            <option value="2">کیش</option>
        </select>
    </div>
</template>

<script>

export default {
    name: 'CustomSelect',
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
    @import './custom-select';
</style>

