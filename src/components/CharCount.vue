<template>
  <div id="char-count">
    <p>{{ params.label }}: {{ count }}</p>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'

export interface CharCountParams {
  label: string
  inputText: string
}
// (Notice that the TypeScript’s string is all lowercase, while Vue’s prop type String is capitalized.)
// 이거 맨날 헷갈림 ㅠ

export default defineComponent({
  name: 'CharCount',
  props: {
    params: {
      type: Object as PropType<CharCountParams>,
      required: true,
    },
  },
  computed: {
    count(): number {
      return this.params.inputText.length
    }
  }
})
</script>