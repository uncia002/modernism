<template>
  <div class="Anime">
    <div class="">
      <div id="motionPath">
        <div class="motion-path">
          <div class="square small el follow-path"></div>
          <svg width="256" height="112" viewBox="0 0 256 112">
            <path fill="none" stroke="currentColor" stroke-width="1" d="M8,56 C8,33.90861 25.90861,16 48,16 C70.09139,16 88,33.90861 88,56 C88,78.09139 105.90861,92 128,92 C150.09139,92 160,72 160,56 C160,40 148,24 128,24 C108,24 96,40 96,56 C96,72 105.90861,92 128,92 C154,93 168,78 168,56 C168,33.90861 185.90861,16 208,16 C230.09139,16 248,33.90861 248,56 C248,78.09139 230.09139,96 208,96 L48,96 C25.90861,96 8,78.09139 8,56 Z"></path>
          </svg>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

import anime from 'animejs';
export default {
  data() {
    return {
    }
  },
  mounted(){
    var path = anime.path('#motionPath path');

    var motionPath = anime({
      targets: '#motionPath .el',
      translateX: path('x'),
      translateY: path('y'),
      rotate: path('angle'),
      easing: 'linear',
      duration: 2000,
      loop: true
    });
  },
  update(){

  }
}
</script>

<style lang="scss">
.Anime{
  font-family: ta;
  position: fixed;
  width:100%;
  height: 100%;
}
.square {
  pointer-events: none;
  width: 28px;
  height: 28px;
  margin: 1px;
  font-size: 12px;
}

.small {
  width: 18px;
  height: 18px;
}

.follow-path {
  position: absolute;
  top: -9px;
  left: -9px;
}

</style>
