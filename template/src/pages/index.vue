<template>
  <div>
    <h1>{{title}}</h1>
  </div>
</template>
<script>
//Js部分尽量采用ES6语法，webpack babel插件会转义兼容
export default {
  //组件私有数据（必须是function，而且要return对象类型）
  data () {
    return {
      title: '移动端首页',
      firstName: '',
      lastName: '',
    }
  },
  //父组件传递过来的数据（两种方式声明：1.数组 2.对象）
  //数组方式
  props: ['age'],
  //对象方式
  /*props: {
    age: {
      type: Number,
      default: 0,
      required: true,
      validator: function (value) {
        return value >= 0
      }
    }
  }*/
  //计算属性
  computed: {
    fullName () {
      return this.firstName + this.lastName
    }
  },
  //监听
  watch: {
    title (preVal, newVal) {
        console.log(`改变之前的值：${preVal}；改变之后的值：${newVal}`)
    }
  },
  //函数集，自己封装，便于开发使用
  methods: {
    getCurrentDate () {
      return new Date().toLocaleDateString()
    }
  },
  //生命周期钩子：实例初始化之后，数据观测(data observer) 和 event/watcher 事件配置之前被调用
  beforeCreated () {
    console.log('component before created')
  },
  //生命周期钩子：组件实例完成创建之后调用
  created () {
    console.log('component created')
  },
  //生命周期钩子：组件实例渲染完成时调用
  mounted () {
    console.log('component mounted')
  },
  //要用到哪些子组件（如果组件已是最小粒度，那么可省略该属性）
  components: {
    //ChildComponents
  }
}
</script>
<style lang="less" scoped>

</style>