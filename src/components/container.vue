<template>
  <div class="container">
    <h1 class="title">Mathify</h1>
    <p class="description">
      使用Latex语法将其转化为数学公式。兼容word🎊<br />问题反馈请点击右下角🚀
    </p>
  </div>
</template>

<script setup>
const startUsing = () => {
  // 处理开始使用逻辑
  console.log("开始使用");
};

const viewTutorial = () => {
  // 处理查看教程逻辑
  console.log("查看教程");
};
</script>

<style scoped>
.container {
  position: relative;
  z-index: 1;
  background: transparent;
  border-radius: 16px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
  padding: 3rem;
  margin: 2rem;
  max-width: 640px;
  max-width: 640px;
  width: 70vw;
}

@keyframes particleMove {
  from {
    background-position: 0 0;
  }
  to {
    background-position: 52px 26px;
  }
}

/* 原有样式调整 */
.title {
  /* 添加文字阴影增强可读性 */
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

p {
  color: #ccc;
  font-size: 14px;
}

/* 移动端适配调整 */
@media (max-width: 768px) {
  .container {
    margin: 1rem;
    padding: 2rem;
  }

  .background {
    background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
  }
}
</style>
