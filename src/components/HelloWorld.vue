<script lang="ts" setup>
import {renderToString} from "katex";
import {onMounted, ref, watch} from "vue";

const count = ref<string>("");
const show = ref<string>("");
const inputfunction = () => {
  show.value = renderToString(count.value, {
    throwOnError: false, //避免错误崩溃
    displayMode: true,
    output: "mathml",
  });
};
watch(
    () => {
      return count.value;
    },
    () => {
      inputfunction();
    },
);

onMounted(() => {
});
</script>
<template>
  <div class="card">
    <div class="card-container">
      <input v-model="count" class="card-body" placeholder="请输入"/>
      <div id="content" v-html="show"></div>
    </div>
  </div>
</template>

<style scoped>
/* 页面整体居中 */
.card {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100vw;
}

/* 卡片容器 */
.card-container {
  position: relative;
  width: 350px;
  padding: 20px;
  border-radius: 12px;
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
  overflow: hidden;
}

/* 文字输入框 */
.card-body {
  background: #1a1a1a;
  width: 100%;
  min-height: 40px;
  padding-left: 10px;
  border: 1px solid #ccc;
  border-radius: 6px;
  font-size: 14px;
  outline: none;
}

/* LaTeX 公式显示区域 */
#content {
  color: #535bf2;
  border: 1px solid #a0b3d6;
  width: 100%;
  min-height: 50px;
  margin-top: 10px;
  padding: 5px;
  border-radius: 6px;
  background: #f1f1f1;
  text-align: center;
}

/* 让彩色边框部分沿四周移动 */
@keyframes borderMove {
  0% {
    background-position: 0% 50%;
  }
  100% {
    background-position: 100% 50%;
  }
}
</style>
