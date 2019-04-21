<template>
<div>
  <div class="select-form">
    <select>
      <option value="">Option 1</option>
      <option value="">Option 2</option>
      <option value="">Option 3</option>
    </select>
  </div>
</div>
</template>

<script>
export default {
  name: 'Dropdown',
  created() {
    console.log(this.$root.$children[0])
  }
}
</script>

<style scoped lang="scss">
.select-form {
  display: block;
  position: relative;
  width: 198px;
  height: 38px;
  line-height: 40px;
  border: 1px solid #ddd;
  text-align: left;
  
  & select {
    width: 100%;
    height: 100%;
    padding: 0 30px 0 10px;
    background-color: transparent;
    border: 0 none;
    font-size: 16px;
    appearance: none;
    -moz-appearance: none;
    -webkit-appearance: none;
  }

  &::after {
    position: absolute;
    top: 16px;
    right: 10px;
    background: url('/select.png') no-repeat 0 0 ;
    width: 13px;
    height: 7px;
    display: block;
    content:'';
  }
}
</style>
