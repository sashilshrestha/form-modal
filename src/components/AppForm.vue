<template>
  <div class="form-container">
    <h1>Contact Us</h1>
    <app-input
      :label="formItem.label"
      :placeholder="formItem.placeholder"
      :type="formItem.type"
      v-for="formItem in $options.FORM_DATA"
      :key="formItem.id"
    ></app-input>
    <div class="input-group">
      <label>Message *</label>
      <textarea
        name=""
        id=""
        cols="30"
        rows="10"
        placeholder="Bitte schreiben Sie uns Ihr Anliegen"
      ></textarea>
    </div>
    <div class="checkbox-group">
      <input type="checkbox" />
      <span>I agree to Terms & Conditions and Privacy Policy.</span>
    </div>
    <button type="submit" @click="$emit('open-modal')">
      Open NewsLetter Modal
    </button>
  </div>
</template>

<script>
import AppInput from './AppInput.vue';

const FORM_DATA = [
  {
    id: 1,
    label: 'E-Mail-Adresse *',
    placeholder: 'ex. name@email.com',
    type: 'text',
  },
  {
    id: 2,
    label: 'Auftrags ID *',
    placeholder: 'Ex . #000000',
    type: 'number',
  },
  {
    id: 3,
    label: 'Subejct *',
    placeholder: 'Subject',
    type: 'text',
  },
];

export default {
  FORM_DATA,
  components: {
    AppInput,
  },
};
</script>

<style lang="scss" scoped>
.form-container {
  border: 1px solid #cfcfcf;
  max-width: 538px;
  width: 100%;
  padding: 24px 32px;

  h1 {
    font-size: 24px;
    margin: 0 0 20px 0;
  }
}
</style>
