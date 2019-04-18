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
        <form method="post" action="#">
          <app-custom-input class="input-component"></app-custom-input>
          <app-custom-input class="input-component"></app-custom-input>
          <app-custom-input class="input-component"></app-custom-input>

          <!-- INPUT RELATED TO THE NATIONALCODE -->
          <app-custom-input v-model="inputValue" class="input-component"></app-custom-input>
          <!-- <p>{{inputValue}}</p> -->

          <app-custom-input class="input-component"></app-custom-input>
          <app-custom-input class="input-component"></app-custom-input>
          <app-custom-select class="select-component"></app-custom-select>
          <app-custom-select class="select-component"></app-custom-select>
          <app-custom-text-area class="text-area-component"></app-custom-text-area>
          <app-custom-input class="input-component"></app-custom-input>
          <app-custom-input class="input-component"></app-custom-input>
        </form>
          <!-- STYLE THE HR TAG LATER -->
          <hr>
          <div class="btn-box">
            <app-button @click.native="nationalCodeChecker" color="regular" class="confBtn">مرحله بعد</app-button>
            <span><a href="#">انصراف</a><span class="seperator">|</span><a href="#">مرحله قبل</a></span>
          </div>
      </div>
    </div>
  </div>
</template>

<script>

import Header from '@/components/Header/Header';
import Button from '@/components/Button/Button';
import CustomInput from '@/components/CustomInput/CustomInput';
import CustomSelect from '@/components/CustomSelect/CustomSelect';
import CustomTextArea from '@/components/CustomTextArea/CustomTextArea';

export default {
  name: 'Home',
  data () {
    return {
      nationalCode : [],
      controllerNumber : 0,
      sumResult : 0,
      remainder : 0,
      inputValue : ''
    }
  },
  components: {
    appButton : Button,
    appCustomInput : CustomInput,
    appHeader : Header,
    appCustomSelect : CustomSelect,
    appCustomTextArea : CustomTextArea
  },
  methods: {
      // THE MAIN FUNCTION 
      nationalCodeChecker() {
      if(this.inputValue.length == 10) {
        this.pushToArray();
        this.isValidCode();
      }else if(this.inputValue.length < 10 && this.inputValue.length >= 8) {
        this.insertZero();
        this.pushToArray();
        this.isValidCode();
      }else if (this.inputValue.length < 8 ) {
        alert("حداقل تعداد ارقام کد ملی باید ۸ رقم باشد. لطفا دوباره کد ملی خود را وارد نمایید.");
      }
      
    },

    // INSERT ZERO(s) AT THE BEGINNING OF THE NATIONAL CODE 
    insertZero() {
      while(this.inputValue.length < 10) {
        this.inputValue = "0" + this.inputValue;
      }
    },

    // CHANGE THE INPUT VALUE TO STRING AND PUSH EACH INDIVIDUAL DIGIT INTO THE ARRAY
    pushToArray() {
      for(let i=0; i< 10; i++) {
        this.nationalCode.push(parseInt(this.inputValue.charAt(i)));
      }
    },

    // EVALUTE THE ENTERED NATIONAL CODE 
    isValidCode() {
      this.controllerNumber = this.nationalCode[9];
      for(let j= 8; j >= 0; j--) {
        this.sumResult += (this.nationalCode[j] * (10-j));
      }
      this.remainder = this.sumResult % 11;
      if((this.remainder < 2) && (this.remainder == this.controllerNumber)) {
        alert("کد ملی وارد شده معتبر می باشد");
      }else if((this.remainder > 2) && ((11 - this.remainder) == this.controllerNumber)) {
        alert("کد ملی وارد شده معتبر می باشد");
      }else {
        alert("کد ملی وارد شده صحیح نیست!");
      }
    }
  }
}
</script>

<style lang="scss">
  @import './home';
</style>

