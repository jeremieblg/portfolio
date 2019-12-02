<template>
  <div class="skillGroup">
    <span @click="displaySkill">{{ capitalizeFirstLetter(title) }}</span>
    <div v-if="open" class="line">
      <skill
        v-for="ability in skill"
        :key="ability.id"
        :name="ability.name"
        :logo-path="ability.logoPath"
      />
    </div>
  </div>
</template>

<script>
import skill from '~/components/skill/skill'
export default {
  components: {
    skill
  },
  props: {
    skill: {
      type: Array,
      default() {
        return {}
      }
    },
    title: {
      type: String,
      default: ''
    }
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
    displaySkill() {
      this.open = !this.open
    }
  }
}
</script>
<style lang="scss">
.skillGroup {
  display: flex;
  flex-direction: column;
  width: 84%;
  margin: 20px 0 20px 0;
  span {
    width: max-content;
    cursor: pointer;
    margin-bottom: 5px;
    user-select: none;
  }
  .line {
    display: flex;
    flex-wrap: wrap;
  }
}
</style>
