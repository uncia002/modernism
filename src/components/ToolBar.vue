<template>
  <div class="toolbar" id="toolbar">
    <h1 @click="displaytool()">TOOL</h1>
    <div class="list">
      <StopWatch/>
    </div>
  </div>
</template>

<script>
import StopWatch from '@/components/StopWatch.vue'
import anime from 'animejs';
export default {
  components:{
    StopWatch,
  },
  data() {
    return {
      state:false
    }
  },
  mounted(){
  },
  computed:{
  },
  methods: {
    displaytool(){
      this.state=!this.state
      console.log(this.state)
      if (this.state==true){
        var cssSelector = anime({
          targets: '#toolbar',
          bottom: '0px',
          easing: 'easeInOutQuad'
        })
      }else{
        var cssSelector = anime({
          targets: '#toolbar',
          bottom: '-230px',
          easing: 'easeInOutQuad'
        })
      }
    }
  }
}
</script>

<style>
.toolbar{
  position: fixed;
  left:50%;
  bottom: -230px;
  transform:  translateX(-50%);
  width:100%;
}
.toolbar h1{
  font-size: 30px;
  margin:0;
}
.s{
  width: 0;
  height: 0;
  border-style: solid;
  border-width: 10px 10px 0 10px;
  border-color: #ffffff transparent transparent transparent;
  margin: 0 auto;
}
.list{

}
</style>
