<template>
  <div>
    <headerComponent />
    <listSkillGroup />
  </div>
</template>
<script>
import headerComponent from '~/components/shared/header/header'
import listSkillGroup from '~/components/skill/listSkillGroup'

export default {
  components: {
    headerComponent,
    listSkillGroup
  }
}
</script>

<style lang="scss"></style>
