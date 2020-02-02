<template>
  <div class="headerSection">
    <div class="headerWrapper">
      <div class="headerLogo">
        <div>Bellanger Jérémie</div>
      </div>
      <div class="headerNav">
        <div
          v-for="(value, index) in navList"
          :key="value.id"
          :class="navList[index].isActive"
          @click="changeAnchor(index)"
        >
          {{ value.nom }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      temp: 0,
      navList: {
        0: {
          nom: 'Présentation',
          isActive: 'active'
        },
        1: {
          nom: 'Création',
          isActive: ''
        },
        2: {
          nom: 'Compétence',
          isActive: ''
        },
        3: {
          nom: 'Parcours',
          isActive: ''
        },
        4: {
          nom: 'Contact',
          isActive: ''
        }
      }
    }
  },
  methods: {
    changeAnchor(index) {
      this.navList[index].isActive = 'active'
      this.navList[this.temp].isActive = ''
      this.temp = index
    }
  }
}
</script>
<style lang="scss">
.headerSection {
  font-size: 20px;
  display: flex;
  justify-content: center;
  height: 90px;
  width: 100%;
  padding: 20px 0;
  background: #353535;
  padding-bottom: 20px;
  padding-top: 20px;
  .headerWrapper {
    display: flex;
    width: 80%;
    justify-content: space-between;
    .headerLogo {
      display: flex;
      width: 50%;
      color: #fff;
      align-items: center;
    }
    @include xl {
      .headerNav {
        width: 600px;
        min-width: 600px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        div {
          color: #fff;
          opacity: 0.5;
          height: max-content;
          position: relative;
          &:hover {
            opacity: 1;
            cursor: pointer;
          }
          &:before {
            content: '';
            background: red;
            width: 0px;
            height: 2px;
            position: absolute;
            bottom: 0;
            left: 0;
            -webkit-transition: width 0.25s ease;
            transition: width 0.25s ease;
          }
        }
        .active {
          opacity: 1;
          &:before {
            width: 50px;
            background-color: red;
          }
        }
      }
    }
  }
}
</style>
