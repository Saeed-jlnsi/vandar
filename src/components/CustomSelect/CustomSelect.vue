<template>
    <div class="select-wrapper">
        <label class="form-label" for="">این تست است<span class="star-icon">*</span></label>
        <select class="form-select">
            <option value="0">انتخاب کنید</option>
            <option value="1">تست</option>
            <option value="2">تست</option>
        </select>
    </div>
</template>

<script>

export default {
    name: 'CustomSelect',
    data () {
        return {  

        }
    }
}
</script>

<style lang="scss">
    @import './custom-select';
</style>

