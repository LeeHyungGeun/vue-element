<template>
  <div>
    <Radio name="fruit" value="apple" label="Apple" id="fruit1" :model="model" />
    <Radio name="fruit" value="pineapple" label="Pineapple" id="fruit2" :model="model" />
    {{model.fruit}}
  </div>
</template>

<script>
import Dropdown from './components/Dropdown.vue'
import Check from './components/Check.vue'
import Radio from './components/Radio.vue'

export default {
  name: 'app',
  data() {
    return {
      isChecked: true,
      model: {
        fruit: 'apple'
      }
    }
  },
  components: {
    /* eslint-disable */
    Dropdown, Check, Radio
  }
}
</script>

<style>
</style>
