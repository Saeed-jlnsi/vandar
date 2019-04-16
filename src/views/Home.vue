<template>
  <div>
    <app-header></app-header>
    <div class="container">
      <h2>کسب و کار جدید</h2>
      <!-- <img src="../assets/img/ثبت کسب و کار جدید.svg" alt=""> -->
      <div class="form-header">
        <span>نوع کسب و کار</span>
        <span class="active-tab">اطلاعات کسب‌و‌کار</span>
        <span>بارگزاری</span>
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

