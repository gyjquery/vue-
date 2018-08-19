<template>
  <div id="app">
     <div id="div1" @click="isShow=!isShow">点击我</div>
    <transition name="fade" @after-leave="myleave">
    <ul v-show="isShow">
      <li>选项一</li>
      <li>选项二</li>
      <li>选项三</li>
      <li>选项四</li>
      <li>选项五</li>
    </ul>
    </transition>
    <template>
      <div class="hello">
        <picture-input
          ref="pictureInput"
          width="600"
          height="600"
          margin="16"
          accept="image/jpeg,image/png"
          size="10"
          button-class="btn"
          :custom-strings="{
        upload: '<h1>haha</h1>',
        drag: '点击选择图片'
      }"
          @change="onChange">
        </picture-input>
      </div>
    </template>
    <div class="div2" :class="{div1:isOn}" @click="isOn=!isOn">sda</div>
    <div>
      <p>121</p>
      <p>121</p>
      <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p>
      <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p>
      <p>121</p>
      <p>121</p>
      <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p>
      <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p> <p>121</p>
    </div>
     <Gotop/>
  </div>
</template>

<script>
  import PictureInput from 'vue-picture-input'
  import Gotop from './components/Gotop.vue'
  export default {
  name: 'App',
  data(){
    return{
      isShow:false,
      isOn:false,
      data: []
    }
  },
  methods:{
    myleave(){
      alert(1)
    },
    onChange (image) {
      console.log(image)
      if (image) {
        console.log(image)
        this.image = image
      } else {
        console.log(3)
      }
    }
  },
    components:{
      PictureInput,
      Gotop
    }

}
</script>

<style scoped>
  #app{
    background: deepskyblue;
    position: relative;
  }
  #div1{
    font-size: 40px;
  }
  ul{
    list-style: none;
    background: deeppink;
    justify-content: space-around;
    display: flex;
    position: absolute;
    width:100%;

  }
  li{
    height:50px;
    line-height: 50px;
  }
  .fade-enter-active, .fade-leave-active {
    transition: .5s
  }
  .fade-enter, .fade-leave-active {
   opacity: 0;
  }
  .div2{
    position: absolute;
    left:0;
    background: #ff0;
    transition: 1s left;
    font-size: 40px;
  }
  .div1{
    left:300px;
  }

</style>
