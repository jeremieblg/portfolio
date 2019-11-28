<template>
  <div class="list">
    <block
      v-for="(skill, index) in listSkill"
      :key="skill.id"
      :skill="skill"
      :title="index"
    />
  </div>
</template>

<script>
import data from '~/src/dataAccess.js'
import block from '~/components/block.vue'

export default {
  components: {
    block
  },
  data() {
    return {
      listSkill: data.competences
    }
  }
}
</script>
<style lang="scss">
.list {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  flex-direction: column;
}
</style>
