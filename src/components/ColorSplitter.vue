<template>
  <div class="colorSplitter">
    <div class="colorSplitter__set" v-for="set in sets" :key="set.toString()">
      <div
      class="colorSplitter__element"
      v-for="element in set"
      :key="set.toString()+element">
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
    }
  },
  computed: {
    uniqueElements() {
      return this.data
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
