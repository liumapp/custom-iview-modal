/**
 * @file formModal.vue
 * @author liumapp
 * @email liumapp.com@gmail.com
 * @homepage http://www.liumapp.com
 * @date 5/28/18
 */
<template>
<div>
  <Input v-model="value1" @on-change="value1Change" />
</div>
</template>
<script>
export default {
  name: 'formModal',
  data () {
    return {
      value1: ''
    }
  },
  methods: {
    value1Change () {
      this.$emit('value1', this.value1);
    }
  }
}
</script>
