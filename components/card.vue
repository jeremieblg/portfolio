<template>
  <div class="card" :class="isOpen">
    <img :src="logoPath" alt />
    <div class="wrapper" @click="openCard()"></div>
    <div class="text">{{ name }}</div>
    <div v-if="open" class="desc" :class="descOpen" @click="openCard()"></div>
  </div>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      default: ''
    },
    logoPath: {
      type: String,
      default: ''
    }
  },
  data() {
    return {
      open: false,
      isOpen: '',
      descOpen: ''
    }
  },
  watch: {
    open(val) {
      if (val) {
        this.isOpen = 'card-open'
        this.descOpen = 'desc-open'
      } else {
        this.isOpen = ''
        this.descOpen = 'desc-close'
      }
    }
  },
  methods: {
    openCard() {
      this.open = !this.open
    }
  }
}
</script>
<style lang="scss">
$duration: 0.45s;
$height-card: 150px;
$wrapper-color: rgba(121, 120, 120, 0.308);
.card {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  transition: 0.3s;
  height: $height-card;
  width: $height-card;
  display: flex;
  position: relative;
  &:hover {
    box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
    cursor: pointer;
    .text {
      display: block;
      animation-duration: $duration;
      animation-name: up;
      top: 50%;
      transform: translateY(-50%);
      cursor: pointer;
      font-family: 'Roboto', sans-serif;
      font-weight: 700;
    }
    .wrapper {
      animation-duration: $duration;
      animation-name: transition;
      opacity: 1;
    }
    img {
      transition: $duration;
      filter: blur(4px);
    }
  }
  img {
    margin: auto;
    height: ($height-card - 50px);
    width: auto;
    z-index: 0;
    filter: blur(0);
  }
  .text {
    display: none;
    position: absolute;
    margin-left: auto;
    margin-right: auto;
    left: 0;
    right: 0;
    font-family: 'Roboto', sans-serif;
  }
  .wrapper {
    height: $height-card;
    width: $height-card;
    position: absolute;
    z-index: 1;
    opacity: 0;
    background-color: $wrapper-color;
  }
  .desc {
    z-index: 2;
    position: absolute;
    height: 150px;
    width: 150px;
    background-color: gray;
  }
  .desc-open {
    animation-duration: $duration;
    animation-name: heigher;
    height: 300px;
    width: 300px;
  }
  .desc-close {
    animation-duration: $duration;
    animation-name: no;
    height: 150px;
    width: 150px;
  }
}
@keyframes up {
  from {
    top: 75%;
  }

  to {
    top: 50%;
    transform: translateY(-50%);
  }
}
@keyframes transition {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
@keyframes heigher {
  0% {
    height: 150px;
    width: 150px;
  }
  100% {
    height: 300px;
    width: 300px;
  }
}
@keyframes no {
  0% {
    height: 300px;
    width: 300px;
  }
  100% {
    height: 150px;
    width: 150px;
  }
}
</style>
