<template>
  <div class="button-wrapper">
    <div class="btn">
            <slot>Button</slot>
        </div>
    </div>
</template>

<script>

export default {
  name: 'Button',
  data () {
    return {

    }
  }
}
</script>

<style lang="scss">
  @import './button';
</style>

