<template>
  <div class="stopwatch">

    <h3>STOP WATCH</h3>
    <div class="time">
      <h1>{{ hours }}:</h1>
      <h1>{{ minutes }}:</h1>
      <h1>{{ seconds }}</h1>
    </div>
    <div class="form">
      <div class="start" @click="startWatch()">
      </div>
      <div class="stop">
      </div>
      <div class="reset">
      </div>
    </div>
  </div>
</template>

<script>


export default {
  data() {
    return {
      hours:"00",
      minutes:"00",
      seconds:"00",
      t_h:0,
      t_m:0,
      t_s:0,
      active:false
    }
  },
  computed:{
  },
  methods: {
    zeroPadding(num, len) {
    　 let zero = ''
      for(var i = 0; i < len; i++) {
        zero += '0'
      }
      return (zero + num).slice(-len);
    },
    startWatch(){
      if (this.active==false){
        this.active=true
        let timerID = setInterval(this.updateTime, 1000);
      }

    },
    updateTime(){
      this.t_s++
      if (this.t_s==59){
        this.t_s=0
        this.t_m++
        if (this.t_m==60) {
          this.t_m=0
          this.t_h++
          this.hours=this.zeroPadding(this.t_h,2)
        }
        this.minutes=this.zeroPadding(this.t_m,2)
      }
      this.seconds=this.zeroPadding(this.t_s,2)
    }
  }
}
</script>

<style scoped>
.stopwatch{
  width: 300px;
  height: 200px;
  margin: 20px;
  border-right: 1px solid white;
}
.time{
  margin:auto;
  display: flex;
  justify-content: center;
}
h3{
  margin:0;
  margin-bottom: 10px;
}
h1{
  font-size: 70px;
}
.form{
  display: flex;
  justify-content: center;
}

.start{
  width: 30px;
  height: 30px;
  background-color: white;
}
.stop{
  width: 30px;
  height: 30px;
  background-color: white;
  margin:0 40px;
}
.reset{
  width: 30px;
  height: 30px;
  background-color: white;
}

</style>
