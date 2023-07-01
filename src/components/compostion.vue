<script setup lang="ts">
import { computed, reactive, ref, watch } from "vue";

const props = defineProps(["age"]);

const name = ref("Compostion");
const names = reactive(["Daniel", "Nell"]);
const formatedFone = ref("");

function addName() {
  names.push(name.value);
}

const computedNames = computed(() => {
  return names;
});

watch(name, async (newName) => {
  var Regex = /(\d{2})(\d)/;
  formatedFone.value = newName.replace(Regex, "($1) $2");
});
</script>

<template>
  <div>
    <div>
      <input v-model="name" />
      <button @click="addName">Adicionar Nome</button>
      {{ formatedFone }}
    </div>

    <div>
      <ul>
        <li>{{ name }}</li>
        <li>{{ props.age }}</li>
      </ul>
    </div>

    <div>
      <ul>
        <li v-for="name in computedNames">{{ name }}</li>
      </ul>
    </div>
  </div>
</template>
