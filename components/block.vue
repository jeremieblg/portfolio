<template>
  <div class="block">
    <span @click="displayCard">{{ capitalizeFirstLetter(title) }}</span>
    <div v-if="open" class="line">
      <card
        v-for="ability in skill"
        :key="ability.id"
        :name="ability.name"
        :logo-path="ability.logoPath"
      />
    </div>
  </div>
</template>

<script>
import card from '~/components/card.vue'
export default {
  props: {
    skill: {
      type: Object,
      default() {
        return {}
      }
    },
    title: {
      type: String,
      default: ''
    }
  },
  components: {
    card
  },
  data() {
    return {
      open: true
    }
  },
  methods: {
    capitalizeFirstLetter(string) {
      return string.charAt(0).toUpperCase() + string.slice(1)
    },
    displayCard() {
      this.open = !this.open
    }
  }
}
</script>
<style lang="scss">
.block {
  display: flex;
  flex-direction: column;
  width: 84%;
  margin: 20px 0 20px 0;
  span {
    width: max-content;
    cursor: pointer;
    margin-bottom: 5px;
  }
  .line {
    display: flex;
    flex-wrap: wrap;
  }
}
</style>
