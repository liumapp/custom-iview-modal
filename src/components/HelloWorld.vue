/**
 * @file HelloWorld.vue
 * @author liumapp
 * @email liumapp.com@gmail.com
 * @homepage http://www.liumapp.com
 * @date 5/28/18
 */
<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>
    <ul>
      <li><button @click="showView">only view</button></li>
      <li><button @click="withForm">with form</button></li>
    </ul>
  </div>
</template>
<script>
import modalDetail from './modalDetail.vue'
import formModal from './formModal.vue'
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  components: {
    modalDetail, formModal
  },
  methods: {
    showView () {
      this.$Message.info('only view modal showed');
      this.$Modal.info({
        scrollable: true,
        render: h => {
          return h(modalDetail, {
            scrollable: true,
            props: {
              value: {
                name: '张三',
                sex: '男',
                age: 16
              }
            }
          });
        }
      })
    },
    withForm () {
      this.$Message.info('modal with form showed');
      this.$Modal.info({
        scrollable: true,
        render: h => {
          return h(formModal, {
            on: {
              value1: (value1) => {
                this.$Message.info('we get value1 from formModal ! and value is : ' + value1);
              }
            }
          })
        }
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
