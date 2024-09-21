<script setup lang="ts">
const url = window?.document?.URL;
interface A {
  a: string,
  b: string,
}
const a: A = {
  a: 'a',
  b: url,
};
const logFunction = (object: A) => {
  console.log(`URL: ${object.b}`);
}
logFunction(a);
const hello = ref('Hello World');
const inputVal = ref('');

watchEffect(() => {
  hello.value = inputVal.value ? inputVal.value : 'Hello World';
  console.log(inputVal.value);
});

</script>

<template>
  <h1>
    {{hello}}
  </h1>
  <hr>
  <input v-model="inputVal"/>
</template>
