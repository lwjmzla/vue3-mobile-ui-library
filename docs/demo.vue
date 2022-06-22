
<script>
import { defineComponent, h, ref, getCurrentInstance } from 'vue'
export default defineComponent({
  props: {
    level: {
      type: Number,
      required: true
    }
  },
  data () {
    return {
      a: 1
    }
  },
  setup () {
    const lwj = ref({ name: '', age: 0 })
    lwj.value.name = 'lwj'
    return {
      b: 1,
      lwj
    }
  },
  created () {
    console.log(this.b, 'created')
  },
  render () {
    const { proxy } = getCurrentInstance()
    console.log(proxy)
    console.log(this.$data)
    console.log(this.$data.a)
    console.log(this.$props.level)
    console.log(this.$options)
    return h(
      'h' + this.level, // 标签名
      {}, // prop 或 attribute
      this.$slots.default() // 包含其子节点的数组
    )
  }
})
</script>
