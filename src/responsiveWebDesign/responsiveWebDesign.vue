<script setup lang="ts">

</script>

<template>
<!--
默认断点
sm	40rem (640px)	@media (width >= 40rem) { ... }
md	48rem (768px)	@media (width >= 48rem) { ... }
lg	64rem (1024px)	@media (width >= 64rem) { ... }
xl	80rem (1280px)	@media (width >= 80rem) { ... }
2xl	96rem (1536px)	@media (width >= 96rem) { ... }
-->
  <div class="mx-auto max-w-md overflow-hidden rounded-xl bg-white shadow-md md:max-w-2xl">
    <div class="md:flex">
      <div class="md:shrink-0">
      </div>
      <div class="p-8">
        <div class="text-sm font-semibold tracking-wide text-indigo-500 uppercase">Company retreats</div>
        <a href="#" class="mt-1 block text-lg leading-tight font-medium text-black hover:underline">
          Incredible accommodation for your team
        </a>
        <p class="mt-2 text-gray-500">
          Looking to take your team away on a retreat to enjoy awesome food and take in some sunshine? We have a list of
          places to do just that.
        </p>
      </div>
    </div>
  </div>
<!-- 移动端优先 不要把 sm: 当成 "在小屏幕上" 的意思，把它当成 "在小断点处"。-->
  <div class="text-center sm:text-left"></div>

<!-- 针对断点范围  md到xl  -->
  <div class="md:max-xl:flex">
    <!-- ... -->
  </div>

<!-- 使用自定义断点 使用 --breakpoint-* 主题变量自定义断点：​​ -->
<!--
 @import "tailwindcss";
  @theme {
    --breakpoint-xs: 30rem;
    --breakpoint-2xl: 100rem;
    --breakpoint-3xl: 120rem;
  }
 -->

<!-- 要删除默认断点，请将其值重置为 initial 关键字： -->
<!--
 @import "tailwindcss";
@theme {
  --breakpoint-2xl: initial;
  --breakpoint-*: initial    删除全部断点
}
 -->

<!-- 使用任意值 -->
  <div class="max-[600px]:bg-sky-300 min-[320px]:text-center">
    <!-- ... -->
  </div>

<!-- 容器查询 是一项现代 CSS 功能，可让你根据父元素的大小而不是整个视口的大小来设置样式。它们让你可以构建更便携和可重用的组件，因为它们可以根据该组件可用的实际空间进行更改。 -->
  <div class="@container">
    <div class="flex flex-col @md:flex-row">
      <!-- ... -->
    </div>
  </div>

<!-- 最大宽度容器查询 -->
  <div class="@container">
    <div class="flex flex-row @max-md:flex-col">
      <!-- ... -->
    </div>
  </div>

<!--  容器查询范围 -->
  <div class="@container">
    <div class="flex flex-row @sm:@max-md:flex-col">
      <!-- ... -->
    </div>
  </div>

<!-- 命名容器 -->
  <div class="@container/main">
    <!-- ... -->
    <div class="flex flex-row @sm/main:flex-col">
      <!-- ... -->
    </div>
  </div>

<!-- 使用自定义容器大小  使用 --container-* 主题变量自定义容器大小： -->
<!--
 @import "tailwindcss";
@theme {
  --container-8xl: 96rem;
}
 -->
  <div class="@container">
    <div class="flex flex-col @8xl:flex-row">
      <!-- ... -->
    </div>
  </div>

<!-- 使用任意值 -->
  <div class="@container">
    <div class="flex flex-col @min-[475px]:flex-row">
      <!-- ... -->
    </div>
  </div>
</template>

<style scoped>

</style>