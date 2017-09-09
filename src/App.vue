<template>
  <div id="app">
    <div class="cishu" v-for="(nums,i) in num" >
       <div :flash="num[i]" class="person pt" v-for="(person,index) in persons" :class="num[i]&&item==i?'go'+index:''">
           卡牌{{i}}{{index}}
       </div>
    </div>
      <button class="btn" @click="func"  type="button"></button>
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      flash: false,
      item: 0,
      num: ['false', 'false', 'false', 'false', 'false'],
      persons: [1, 2, 3, 4]
    }
  },
  methods: {
    func () {
      var that = this
      this.num[0] = !this.num[0]
      if (this.item === 5) {
        clearTimeout(tim)
      }
      var tim = setTimeout(function () {
        that.item++
      }, 1000)
    }
  }
}
function a () {
  alert(1)
}
a()
</script>

<style lang="stylus" rel="stylesheet/stylus">
#app
  width: 100%
  height: 100%
.pt
   width: 100px
   height: 100px
   position: absolute
   top: 300px
   left: 300px
   background: red
   transition: transform 0.25s
 .br

.duraing0
   transition-delay: 0s
.duraing1
   transition-delay: 0s
.duraing2
   transition-delay: 0s
.duraing3
   transition-delay: 0s
.go0
   transition-delay: 0s
   transform: translate(-200px,-200px)
.go1
   transition-delay: 0.25s
   transform: translate(-200px,200px)
.go2
   transition-delay: 0.5s
   transform: translate(200px,200px)
.go3
   transition-delay: 0.75s
   transform: translate(200px,-200px)
.btn
  width: 100px
  height: 30px

</style>
