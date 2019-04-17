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
      <div class="registration-form">
        <!-- SHOULD BE LOOPED INSIDE A V-FOR DIRECTIVE -->
        <!-- <form action=""> -->
          <app-custom-input class="input-component"></app-custom-input>
          <app-custom-input class="input-component"></app-custom-input>
          <app-custom-input class="input-component"></app-custom-input>
          <app-custom-input class="input-component"></app-custom-input>
          <app-custom-input class="input-component"></app-custom-input>
          <app-custom-input class="input-component"></app-custom-input>
          <!-- <app-custom-select class="select-component"></app-custom-select>
          <app-custom-select class="select-component"></app-custom-select> -->
          <app-custom-input class="input-component"></app-custom-input>
          <app-custom-input class="input-component"></app-custom-input>
          <app-custom-input class="input-component"></app-custom-input>
        <!-- </form> -->
        <!-- <hr> -->
      </div>
    </div>
  </div>
</template>

<script>

import Header from '@/components/Header/Header';
import Button from '@/components/Button/Button';
import CustomInput from '@/components/CustomInput/CustomInput';
import CustomSelect from '@/components/CustomSelect/CustomSelect';

export default {
  name: 'Home',
  data () {
    return {

    }
  },
  components: {
    appButton : Button,
    appCustomInput : CustomInput,
    appHeader : Header,
    appCustomSelect : CustomSelect
  }

}
</script>

<style lang="scss">
  @import './home';
</style>

