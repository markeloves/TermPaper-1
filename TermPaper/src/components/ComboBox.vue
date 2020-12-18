<template>
    <select v-model="selected"
    @change="get">
        <option disabled value="">Выберите один из вариантов</option>
        <option v-for="item in Items"
        v-bind:key="item.id"
        v-bind:value="item.title">
        {{item.id}}: {{item.title}}
        </option>
    </select>
</template>

<script>
export default {
  props: {
    CurrentElem: {
      type: String,
      required: false,
      default: null
    }
  },
  data () {
    return {
      Items: null,
      selected: ''
    }
  },
  methods: {
    get () {
      this.$emit('get-previous', this.selected)
    }
  },
  mounted () {
    fetch(`https://jsonplaceholder.typicode.com/todos?${this.CurrentElem ? `title=${this.CurrentElem}` : ''}`)
      .then(response => response.json())
      .then(json => {
        this.Items = json
      })
  },
  watch: {
    CurrentElem (value) {
      fetch(`https://jsonplaceholder.typicode.com/todos?${this.CurrentElem ? `title=${this.CurrentElem}` : ''}`)
        .then(response => response.json())
        .then(json => {
          this.Items = json
        })
      console.log(this.CurrentElem, '===', value)
    }
  }
}
</script>

<style scoped>

select {
    font-family: 'Times New Roman', Times, serif;
    font-size: 25px;
    width: 90%;
    border-radius: 5px;
}

option {
    font-family: 'Times New Roman', Times, serif;
    font-size: 25px;
}
</style>
