<template>
  <div style="display: flex; gap: 5;">
    <div class="compostion">
      <Composition :age="age"/>
    </div>
    <Option class="option" :age="age"/>
  </div>
</template>

<script lang="ts">
import Composition from './components/compostion.vue';
import Option from './components/option.vue';

export default {
  data(){
    return {
      age: 18
    }
  },
  components: {
    Composition,
    Option
  }
}
</script>

<style scoped>
.compostion {
  flex: 1;
  background-color: cadetblue;
}

.option {
  flex: 1;
  background-color: #ccc;
}
</style>
