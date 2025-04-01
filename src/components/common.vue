<script lang="ts" setup>
import { ref } from "vue";
import { renderToString } from "katex";

const latexSyntax = ref([
  {
    name: "分数",
    latex: "\\frac{a}{b}",
    description: "`\\frac{a}{b}` 表示分数 a/b",
  },
  {
    name: "平方根",
    latex: "\\sqrt{x}",
    description: "`\\sqrt{x}` 表示平方根 √x",
  },
  {
    name: "上下标",
    latex: "x_i^2",
    description: "`x_i^2` 表示下标 i 和上标 2",
  },
  {
    name: "求和",
    latex: "\\sum_{n=1}^{\\infty} \\frac{1}{n^2}",
    description: "`\\sum_{n=1}^{\\infty} \\frac{1}{n^2}` 表示从 1 到无穷求和",
  },
  {
    name: "积分",
    latex: "\\int_a^b x^2 \\,dx",
    description: "`\\int_a^b x^2 \\,dx` 表示积分",
  },
]);
</script>

<template>
  <div class="syntax-help">
    <h2>LaTeX 语法说明</h2>
    <div class="syntax-list">
      <div
        v-for="(syntax, index) in latexSyntax"
        :key="index"
        class="syntax-item"
      >
        <div class="syntax-title">{{ syntax.name }}</div>
        <div
          class="syntax-example"
          v-html="
            renderToString(syntax.latex, {
              throwOnError: false,
              output: 'mathml',
            })
          "
        ></div>
        <div class="syntax-description">{{ syntax.description }}</div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.syntax-help {
  width: 100%;
  max-width: 350px;
  max-height: 350px;
  padding: 20px;
  background: #f9f9f9;
  border-radius: 12px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  text-align: center;
  overflow: auto;
}

@media (max-width: 768px) {
  .syntax-help {
    max-height: 300px;
    max-width: 350px;
  }
}

h2 {
  font-size: 20px;
  margin-bottom: 16px;
}

.syntax-list {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.syntax-item {
  padding: 12px;
  background: white;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.syntax-title {
  font-weight: bold;
  font-size: 18px;
  margin-bottom: 6px;
}

.syntax-example {
  font-size: 22px;
  margin-bottom: 6px;
}

.syntax-description {
  font-size: 14px;
  color: #555;
  margin-bottom: 8px;
}

.syntax-code {
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-size: 14px;
  color: #333;
  background: #eee;
  padding: 6px 10px;
  border-radius: 6px;
}

button {
  background: #008cba;
  color: white;
  border: none;
  padding: 4px 8px;
  border-radius: 4px;
  cursor: pointer;
  font-size: 14px;
}

button:hover {
  background: #0073a8;
}
</style>
