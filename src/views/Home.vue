<template>
  <div>
    <app-header></app-header>
    <div class="container">
      <h2>کسب و کار جدید</h2>
      <div class="form-header">
        <span>نوع کسب و کار</span>
        <span class="active-tab">اطلاعات کسب‌و‌کار</span>
        <span>بارگزاری</span>
      </div>
      <div class="registration-form">
        <!-- SHOULD BE LOOPED INSIDE A V-FOR DIRECTIVE -->
        <form method="post" action="#">
          <app-custom-input 
            :hasIcon="true" 
            label="نام حقوقی" 
            class="component-element" 
            placeHolder="نامی که در روزنامه رسمی شما آمده است">
          </app-custom-input>
          <app-custom-input 
            :hasIcon="true" 
            label="نام برند" 
            class="component-element" 
            placeHolder="نام کوتاه و اختصاری">
          </app-custom-input>
          <app-custom-input 
            :hasIcon="true" 
            label="نام انگلیسی برند" 
            class="component-element" 
            placeHolder="مثل Vandar">
          </app-custom-input>
          <app-custom-input 
            label="شناسه ملی" 
            v-model="inputValue" 
            class="component-element">
          </app-custom-input>
          <app-custom-input 
            label="شماره شبا" 
            class="component-element" 
            placeHolder="IR430550011480005587452001">
          </app-custom-input>
          <app-custom-input 
            label="حوزه فعالیت" 
            class="component-element">
          </app-custom-input>
          <app-custom-select 
            label="استان" 
            class="component-element">
          </app-custom-select>
          <app-custom-select 
            label="شهر" 
            class="component-element">
          </app-custom-select>
          <app-custom-text-area 
            label="آدرس" 
            class="component-element">
          </app-custom-text-area>
          <app-custom-input 
            label="کد پستی" 
            class="component-element">
          </app-custom-input>
          <app-custom-input 
            label="تلفن ثابت" 
            class="component-element" 
            placeHolder="مثل 22886644">
          </app-custom-input>
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
      label: '',
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

      if (this.inputValue.length < 8 ) {
        alert("حداقل تعداد ارقام کد ملی باید ۸ رقم باشد. لطفا دوباره کد ملی خود را وارد نمایید.");
      }else {
        if(this.inputValue.length < 10) {
          this.insertZero();
        }
        this.pushToArray();
        this.isValidCode();
      }
      console.log(this.inputValue);
      console.log(this.nationalCode);
    },

    // INSERT ZERO(s) AT THE BEGINNING OF THE NATIONAL CODE 
    insertZero() {
      while(this.inputValue.length < 10) {
        this.inputValue = "0" + this.inputValue;
      }
    },

    // CHANGE THE INPUT VALUE TO STRING AND PUSH EACH INDIVIDUAL DIGIT INTO THE ARRAY
    pushToArray() {
      // this.nationalCode = [];
      for(var i=0; i< 10; i++) {
        this.nationalCode.push(parseInt(this.inputValue.charAt(i)));
      }
    },

    // EVALUTE THE ENTERED NATIONAL CODE 
    isValidCode() {
      this.remainder = 0;
      this.sumResult = 0;
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
      this.nationalCode = [];
    }
  }
}
</script>

<style lang="scss">
  @import './home';
</style>

