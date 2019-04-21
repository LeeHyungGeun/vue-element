<template>
  <div>
    <input type="checkbox" :id="id" :name="name" :value="value" :disabled="disabled">
    <label role="checkbox" :for="id">{{label}}</label>
  </div>
</template>

<script>
export default {
  name: 'Checkbox',
  props: {
    label: {},
    model: {},
    disabled: Boolean,
    name: String,
    id: String,
  },
}
</script>

<style scoped lang="scss">
input[type=checkbox] { /* hide input */
  position: absolute;
  overflow: hidden;
  width: 1px;
  height: 1px;
  margin: -1px;
  opacity: 0;

  & + label {
    display: inline-block;
    font-size: 16px;
    cursor: pointer;
    user-select: none;
  }
  & + label:before {
    display: inline-block;
    width: 20px;
    height: 20px;
    margin: -4px 5px 0 0;
    background: url(/img/checkbox.png) no-repeat 0 0;
    background-size: 20px;
    vertical-align: top;
    content: '';
    cursor: pointer;
  }
  &:checked + label:before {
    background-image: url(/img/checkbox_on.png);
    cursor: pointer;
  }
}
</style>
