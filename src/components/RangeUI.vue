<template>
  <div>
    <div class="circle" id="elem"></div>
  </div>
</template>

<script>
import anime from 'animejs';

export default {
  data() {
    return {

    }
  },

  mounted() {
    var cssSelector = anime({
      targets: '#elem',
      translateX: '100px',
      backgroundColor: '#FFF',
      borderRadius: ['0%', '50%'],
      easing: 'easeInOutQuad'
    });
  },

  methods: {
  }
}
</script>

<style>
.circle{
  background-color: #ea0f9b;
  width: 80px;
  height: 80px;
}
</style>
