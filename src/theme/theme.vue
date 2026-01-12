<script setup lang="ts">

</script>

<template>
<!--主题变量  -->
<!--
 @theme {
  --color-mint-500: oklch(0.72 0.11 178);
}
-->
  <div style="background-color: var(--color-mint-500)" class="w-20 h-20">
    <!-- ... -->
  </div>

<!-- 覆盖默认主题 -->
<!--
 @import "tailwindcss";
  @theme {
    --breakpoint-sm: 30rem;
  }
-->

<!-- 使用自定义主题 -->
<!--
 @import "tailwindcss";
@theme {
  --*: initial;
  --spacing: 4px;
  --font-body: Inter, sans-serif;
  --color-lagoon: oklch(0.72 0.11 221.19);
  --color-coral: oklch(0.74 0.17 40.24);
  --color-driftwood: oklch(0.79 0.06 74.59);
  --color-tide: oklch(0.49 0.08 205.88);
  --color-dusk: oklch(0.82 0.15 72.09);
}
 -->

<!-- 定义动画关键帧 -->
<!--
 @import "tailwindcss";
@theme {
  --animate-fade-in-scale: fade-in-scale 0.3s ease-out;
  @keyframes fade-in-scale {
    0% {
      opacity: 0;
      transform: scale(0.95);
    }
    100% {
      opacity: 1;
      transform: scale(1);
    }
  }
}
 -->

<!-- 引用其他变量 定义引用其他变量的主题变量时，请使用 inline 选项： -->
<!--
  @import "tailwindcss";
  @theme inline {
      --font-sans: var(--font-inter);
  }
 -->

<!-- 生成所有 CSS 变量 默认情况下，最终 CSS 输出中只会生成使用的 CSS 变量。如果你想要始终生成所有 CSS 变量，可以使用 static 主题选项： -->
<!--
 @import "tailwindcss";
@theme static {
  --color-primary: var(--color-red-500);
  --color-secondary: var(--color-blue-500);
}
 -->
</template>

<style scoped>

</style>