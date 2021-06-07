<template>
  <div class="Clock">
    <div class="Time">
      <h1>{{ hours }}</h1>
      <h1>:</h1>
      <h1>{{ minutes }}</h1>
      <h1>:</h1>
      <h1>{{ seconds }}</h1>
    </div>
  </div>
</template>

<script>


export default {
  data() {
    return {
      hours:0,
      minutes:0,
      seconds:0,
    }
  },
  mounted(){
　　let timerID = setInterval(this.updateTime, 1000);
  },
  computed:{
  },
  methods: {
    updateTime(){
      let now = new Date()
      this.hours=now.getHours()
      this.minutes=this.zeroPadding(now.getMinutes(), 2)
      this.seconds=this.zeroPadding(now.getSeconds(), 2)
    },
    zeroPadding: function(num, len) {
    　 let zero = '';
     //0の文字列を作成
      for(var i = 0; i < len; i++) {
        zero += '0';
      }
      // zeroの文字列と、数字を結合し、後ろ２文字を返す
      return (zero + num).slice(-len);
    }
  }
}
</script>

<style>
@font-face {
  font-family:'ta';
  src: url("../assets/Modernist.otf");
}

.Clock{
  font-family: ta;
  position: fixed;
  left:50%;
  top: 50%;
  transform: translateY(-50%) translateX(-50%);
  color:white;
}
.Time{
  display:flex;
  font-size:100px ;
}
</style>
