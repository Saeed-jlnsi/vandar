<template>
  <div>
    <app-header></app-header>
    <div class="container">
      <h2>کسب و کار جدید</h2>
      <div class="form-title">
        <span></span>
        <span></span>
        <span></span>
      </div>
    </div>
  </div>
</template>

<script>

import Header from '@/components/Header/Header';
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
    appCustomInput : CustomInput,
    appHeader : Header
  }

}
</script>

<style lang="scss">
  @import './home';
</style>

