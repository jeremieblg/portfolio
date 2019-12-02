<template>
  <div class="list">
    <skillGroup
      v-for="(skill, index) in listSkill"
      :key="skill.id"
      :skill="skill"
      :title="index"
    />
  </div>
</template>

<script>
import data from '~/src/dataAccess.js'
import skillGroup from '~/components/skill/skillGroup'

export default {
  components: {
    skillGroup
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
