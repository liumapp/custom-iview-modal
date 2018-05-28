/**
 * @file modalDetail.vue
 * @author liumapp
 * @email liumapp.com@gmail.com
 * @homepage http://www.liumapp.com
 * @date 5/28/18
 */
<template>
<div>
  name: {{ detail.name }}
  <br>
  sex: {{ detail.sex }}
  <br>
  age: {{ detail.age }}
</div>
</template>
<script>
export default {
  name: 'modalDetail',
  props: {
    value: Object
  },
  data () {
    return {
      detail: {}
    }
  },
  created () {
    this.init();
  },
  watch: {
    value (data) {
      this.init();
    }
  },
  methods: {
    init () {
      this.detail = this.value;
    }
  }
}
</script>
