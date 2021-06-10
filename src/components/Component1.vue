<template>
    <div>
        <div class="row">
            <div class="col">
                <h5>Component 1:</h5>
            </div>
            <div class="col">
                <input v-model="component1Text"/>
            </div>
            <div class="col">
                <h3>{{component2Text}}</h3>
            </div>
        </div>
    </div>
</template>

<script>

export default {
  name: 'Component1',
  props: {
    component2Text: {
        type: String,
        required: false,
    }
  },
  data: function() {
    return {
      component1Text: '',
    }
  },
  watch: {
      component1Text(text){
          console.log(text)
          this.$emit('updateText',text);
      }
  }
}
</script>