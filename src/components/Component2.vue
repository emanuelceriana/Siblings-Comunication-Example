<template>
    <div>
        <div class="row">
            <div class="col">
                <h5>Component 2:</h5>
            </div>
            <div class="col">
                <input v-model="component2Text"/>
            </div>
            <div class="col">
                <h3>{{component1Text}}</h3>
            </div>
        </div>
    </div>
</template>

<script>

export default {
  name: 'Component2',
  props: {
    component1Text: {
        type: String,
        required: false,
    }
  },
  data: function() {
    return {
      component2Text: '',
    }
  },
  watch: {
      component2Text(text){
          this.$emit('updateText',text);
      }
  }
}
</script>