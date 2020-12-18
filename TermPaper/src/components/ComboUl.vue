<template>
    <ul class="list-group">
        <li class="list-group-item">
            <span>Первый</span>
            <br>
            <ComboBox @get-previous="setSecondValue" />
        </li>
        <li class="list-group-item">
            <span>Второй</span>
            <br>
            <ComboBox
            v-if="secValue !== ''"
            :CurrentElem="secValue" @get-previous="setThirdValue"/>
        </li>
        <li class="list-group-item">
            <span>Третий</span>
            <br>
            <ComboBox
            v-if="thiValue !== ''"
            :CurrentElem="thiValue"/>
        </li>
    </ul>
</template>

<script>
import ComboBox from '@/components/ComboBox'
export default {
  components: {
    ComboBox
  },
  data () {
    return {
      secValue: '',
      thiValue: ''
    }
  },
  methods: {
    setSecondValue (value) {
      this.secValue = value
    },
    setThirdValue (value) {
      this.thiValue = value
    }
  }
}
</script>

<style scoped>
.list-group-item {
  text-align: center;
  list-style-type: none;
  font-size: 35px;
}
</style>
