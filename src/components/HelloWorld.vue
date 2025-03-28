<script lang="ts" setup>
import {renderToString} from "katex";
import {onMounted} from "vue";


const count: string = "$$E=mc^2$$"
onMounted(() => {
  const content = document.getElementById("content")
  if (content) {
    content.innerHTML = renderToString(count.replace(/\$\$/g, ""), {
      throwOnError: true,
      displayMode: true,
      output: "mathml"
    });
  }
})

</script>

<template>
  <div class="card">
    <input autocomplete="off" autofocus placeholder="Enter your math expression here" type="text"/>
    <button type="button"></button>
    <div id="content">
    </div>
  </div>
</template>

<style scoped>
input {
  outline: none;
  border: 1px solid #ccc;
  border-radius: 8px;
  
}
</style>
