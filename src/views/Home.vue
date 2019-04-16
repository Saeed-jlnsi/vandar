<template>
  <div>
    <app-button></app-button>
    <app-custom-input></app-custom-input>
  </div>
</template>

<script>

import Button from '@/components/Button/Button';
import CustomInput from '@/components/CustomInput/CustomInput';

export default {
  name: 'Home',
  data () {
    return {

    }
  },
  components: {
    appButton : Button,
    appCustomInput : CustomInput
  }

}
</script>

<style lang="scss">
  @import './home';
</style>

