<template>
  <div class="progress__container"><div class="progress__inner" :style="{width: (count/10)*100 + '%'}">{{count}}/10</div></div>
</template>

<script>
export default {
  name: 'ProgressBar',
  props: {
    count: Number
  },
}
</script>


<style>
    .progress__container {
        width: 100%;
        position: relative;
        height: 24px;
        margin-bottom: 60px;
    }
    .progress__inner {
        position: absolute;
        top: 0;
        left: 0;
        height: 24px;
        background-color: #007bff;
        z-index: 2;
        color: #fff;
        display: flex;
        align-items: center;
        justify-content: center;
        transition: all .5s ease-out;
        overflow: hidden;
    }
</style>
