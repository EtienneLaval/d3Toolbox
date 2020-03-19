<template>
  <div class="colorSplitter">
    <div class="colorSplitter__set" v-for="(set,setIndex) in sets" :key="setIndex">
      <div
      class="colorSplitter__element"
      v-for="(element,elementIndex) in set"
      :key="setIndex+'.'+elementIndex">
        {{element}}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ColorSplitter',
  props: {
    msg: String,
  },
  data() {
    return {
      sets: [
        ['a', 'z', 'e', 'r', 't', 'y', 'u', 'i', 'o', 'p'],
        ['r', 't', 'y', 'u', 'i', 'o', 'p', 'q'],
      ],
      keyColors: [
        [127, 255, 0],
        [0, 250, 154],
        [199, 21, 133],
      ],
      minColorSpace: 50,
    }
  },
  computed: {
    allElements() {
      return this.sets.reduce((acc, set) => [...acc, ...set], [])
    },
    uniqueElements() {
      return this.allElements.filter(this.filterUnique)
    },

  },
  methods: {
    filterUnique(value, index, self) {
      return self.indexOf(value) === index
    },
    getColorVector(KeyColor0, KeyColor1) {
      return [
        KeyColor1[0] - KeyColor0[0],
        KeyColor1[1] - KeyColor0[1],
        KeyColor1[2] - KeyColor0[2],
      ]
    },
    getColorVectorNorm(colorVector) {
      return Math.sqrt(
        colorVector[0] * colorVector[0]
        + colorVector[1] * colorVector[1]
        + colorVector[2] * colorVector[2],
      )
    },

  },
}
</script>

<style scoped lang="scss">
.colorSplitter{
  &__set{
    display: flex;
    justify-content: center;
  }

  &__element{
    color: dimgray;
  }
}
</style>
