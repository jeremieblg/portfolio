<template>
  <div class="container">
    <div>
      <card
        v-for="ability in skill.frontend"
        :key="ability.id"
        :name="ability.name"
        :logo-path="ability.logoPath"
      />
      <card
        v-for="ability in skill.tools"
        :key="ability.id"
        :name="ability.name"
        :logo-path="ability.logoPath"
      />
      <card
        v-for="ability in skill.backend"
        :key="ability.id"
        :name="ability.name"
        :logo-path="ability.logoPath"
      />
      <card
        v-for="ability in skill.cms"
        :key="ability.id"
        :name="ability.name"
        :logo-path="ability.logoPath"
      />
      <card
        v-for="ability in skill.integration"
        :key="ability.id"
        :name="ability.name"
        :logo-path="ability.logoPath"
      />
      <card
        v-for="ability in skill.container"
        :key="ability.id"
        :name="ability.name"
        :logo-path="ability.logoPath"
      />
      <card
        v-for="ability in skill.database"
        :key="ability.id"
        :name="ability.name"
        :logo-path="ability.logoPath"
      />
      <card
        v-for="ability in skill.system"
        :key="ability.id"
        :name="ability.name"
        :logo-path="ability.logoPath"
      />
    </div>
  </div>
</template>

<script>
import data from '~/src/dataAccess.js'
import card from '~/components/card.vue'

export default {
  components: {
    card
  },
  data() {
    return {
      skill: data.competences
    }
  }
}
</script>

<style lang="scss">
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  > div {
    display: flex;
    width: 84%;
    flex-wrap: wrap;
  }
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
