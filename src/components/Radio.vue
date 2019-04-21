<template>
<div>
  <input 
    type="radio" 
    :id="id" 
    :name="name" 
    :disabled="disabled" 
    :value="value" 
    v-model="amodel" 
    @change="handleChange"
  >
  <label :for="id">{{label}}</label>
</div>
</template>

<script>
export default {
  name: 'Radio',
  props: {
    id: String,
    name: String,
    disabled: Boolean,
    label: {},
    model: {},
    value: {},
  },
  data() {
    return {
      amodel: this.model[this.name] || ''
    }
  },
  watch: {
    // model(value) {
    //   this.amodel = value
    // }
  },
  methods: {
    handleChange(e) {
      this.$set(this.model, this.name, e.target.value)
    }
  }
}
</script>

<style scoped lang="scss">
input[type=radio] { /* hide input */
  position: absolute;
  overflow:hidden;
  width: 1px;
  height: 1px;
  margin: -1px;
  opacity: 0;

  & + label {
    display: inline-block;
    font-size: 16px;
    &::before {
      display: inline-block;
      width: 20px;
      height: 20px;
      margin:-4px 5px 0 0;
      background: url(/img/radio.png) no-repeat 0 0;
      background-size: 20px;
      vertical-align: top;
      content:'';
    }
  }
  &:checked + label:before {
    background-image: url(/img/radio_on.png);
  }
}
</style>
